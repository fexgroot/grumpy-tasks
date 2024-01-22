<template>
  <li>
    <div>
      <a href="#" @click="markTask">{{ itemName }}</a>
    </div>
    <div>
      <button @click="deleteItem">✖</button>
    </div>
  </li>
</template>

<script>
export default {
  props: {
    itemName: {
      type: String,
      required: true,
    },
  },
  methods: {
    markTask() {
      this.$emit("mark-task", this.itemName);
    },
    deleteItem() {
      this.$emit("delete");
    },
  },
};
</script>

<style scoped>
li {
  display: flex;
  align-items: center;
  justify-content: space-between;
  font-weight: bold;
  background-color: white;
  padding: 0.5rem 1rem;
  border: 3px solid #ccc;
  border-radius: 0.5rem;
  margin-bottom: 0.5rem;
}
li a {
  color: #35495e;
  text-decoration: none;
}
li a:hover {
  text-decoration: line-through;
  text-decoration-thickness: 1.5px;
  text-decoration-color: rgb(52, 73, 94, 0.5);
}
li a:focus-visible {
  text-decoration: line-through;
  text-decoration-thickness: 1.5px;
  text-decoration-color: rgb(52, 73, 94, 0.5);
  outline: none;
  opacity: 0.5;
}

button {
  border: none;
  border-radius: 100%;
  padding: 0.5rem 0.78rem;
  margin-left: 0.5rem;
  font-size: 1rem;
  cursor: pointer;
  background-color: #35495e;
  color: white;
  transition: 0.1s ease-in-out;
}
button:hover {
  background-color: #d74755;
}
button:focus-visible {
  outline: none;
  opacity: 0.5;
}
</style>
