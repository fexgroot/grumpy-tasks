<template>
  <div>
    <hr v-if="tasks.length > 0" />
    <ul>
      <ItemComponent
        v-for="(task, index) in tasks"
        :key="index"
        :item-name="task"
        @delete="deleteTask(index)"
        @mark-task="markTaskHandler"
      />
    </ul>
  </div>
</template>

<script>
import ItemComponent from "./Item.vue";

export default {
  components: {
    ItemComponent,
  },
  props: {
    tasks: {
      type: Array,
      default: () => [],
    },
  },
  methods: {
    deleteTask(index) {
      this.$emit("delete", index);
    },
    markTaskHandler(taskName) {
      const index = this.tasks.indexOf(taskName);
      if (index > -1) {
        this.tasks.splice(index, 1); // Remove the task from the tasks array

        // Update local storage
        localStorage.setItem("tasks", JSON.stringify(this.tasks));
      }
    },
  },
};
</script>

<style scoped>
hr {
  border: 2px solid rgb(52, 73, 94, 0.2);
  margin: 1rem auto;
  width: 50%; 
}

ul {
  list-style: none;
  padding: 0;
  margin: 0;
  width: 50vw;
}

@media only screen and (max-width: 1024px) {
  ul {
    width: 70vw;
  }
}
</style>
