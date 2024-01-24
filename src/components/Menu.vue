<template>
  <div class="container">
    <div id="menuButton">
      <img src="../assets/menu.svg" alt="Menu" />
    </div>
    <div
      @mouseenter="showMenu = true"
      @mouseleave="showMenu = false"
      class="menuList"
      :class="{ menuOpen: showMenu }"
    >
      <button @click="deleteAllTasks" id="deleteButton">Delete All</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      showMenu: false,
    };
  },
  methods: {
    deleteAllTasks() {
      this.$emit("delete-all-tasks");
      localStorage.setItem("tasks", JSON.stringify([]));
      setTimeout(() => {
        this.showMenu = false;
      }, 500);
    },
  },
};
</script>

<style scoped>
.container {
  position: absolute;
  top: 2rem;
  left: 2rem;
  width: 5vw;
  height: 85vh;
}

.menuList {
  display: flex;
  flex-direction: column;
  position: absolute;
  top: -1rem;
  left: -15%; /* start off screen */
  width: 100%;
  height: 100%;
  padding: 1rem;
  padding-top: 4rem;
  background: lightgray;
  border-radius: 0.8rem;
  opacity: 0;
  box-shadow: 0 0 20px rgba(0, 0, 0, 0.1);
  transition: all 0.1s ease-in-out;
}

.menuOpen {
  visibility: visible;
  opacity: 1;
  left: 1rem;
  width: 250px;
}

#menuButton {
  background: none;
  border: none;
  margin: 0;
  padding: 0;
  transition: 0.1s ease-in-out;
  position: absolute;
  z-index: 1;
  left: -2rem;
  top: 50%;
  transform: rotate(90deg);
}

#deleteButton {
  border: none;
  border-radius: 2rem;
  padding: 0.5rem 0.78rem;
  margin-left: 0.5rem;
  font-size: 1rem;
  cursor: pointer;
  background-color: #35495e;
  color: white;
  transition: 0.1s ease-in-out;
}

#deleteButton:hover {
  background-color: #d74755;
}

#deleteButton:active {
  transform: scale(0.9);
}

#deleteButton:focus-visible {
  outline: none;
  opacity: 0.5;
}
</style>
