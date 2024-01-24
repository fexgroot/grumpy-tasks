<template>
  <div class="wrapper">
    <CounterComponent :taskCount="tasks.length" />
    <MenuComponent @delete-all-tasks="clearAllTasks" />
    <HeaderComponent />
    <InputComponent :placeholder="inputPlaceholder" @add="addTask" />
    <ListComponent :tasks="tasks" @delete="deleteTask" />
    <FooterComponent />
  </div>
</template>

<script>
import CounterComponent from "./components/Counter.vue";
import MenuComponent from "./components/Menu.vue";
import HeaderComponent from "./components/Header.vue";
import InputComponent from "./components/Input.vue";
import ListComponent from "./components/List.vue";
import FooterComponent from "./components/Footer.vue";

export default {
  components: {
    CounterComponent,
    MenuComponent,
    HeaderComponent,
    InputComponent,
    ListComponent,
    FooterComponent,
  },
  data() {
    return {
      tasks: [],
    };
  },
  methods: {
    addTask(task) {
      if (task.trim().length >= 3) {
        this.tasks.unshift(task.trim());
      } else {
        alert("Task must be at least 3 characters long");
      }
    },
    deleteTask(index) {
      this.tasks.splice(index, 1);
    },
    clearAllTasks() {
      this.tasks = []; // Set tasks to an empty array
    },
  },
  computed: {
    inputPlaceholder() {
      return this.tasks.length === 0 ? `Add a new task` : "Add another task";
    },
  },
  mounted() {
    // Load tasks from local storage
    const tasks = JSON.parse(localStorage.getItem("tasks"));
    if (tasks) {
      this.tasks = tasks;
    }
  },
  watch: {
    tasks: {
      handler(newTasks) {
        localStorage.setItem("tasks", JSON.stringify(newTasks));
      },
      deep: true,
    },
  },
};
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Montserrat:wght@400;700;900&display=swap");

.wrapper {
  display: flex;
  flex-direction: column;
  align-items: center;
  font-family: "Montserrat", sans-serif;
  line-height: 1.5;
  padding-left: 6rem;
  padding-right: 6rem;
  padding-top: 2rem;
  padding-bottom: 2rem;
  padding: 0;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  user-select: none;
  color: #35495e;
}
</style>
