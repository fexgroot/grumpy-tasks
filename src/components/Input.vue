<template>
    <div>
        <input
            ref="input"
            v-model="newTask"
            @keyup.enter="addTask"
            :placeholder="placeholder"
            maxlength="50"
        />
    </div>
</template>

<script>
export default {
    props: {
        placeholder: {
            type: String,
            default: "Add a new task",
        },
    },
    data() {
        return {
            newTask: "",
        };
    },
    methods: {
        addTask() {
            if (this.newTask.trim() !== "") {
                this.$emit("add", this.newTask.trim());
                this.newTask = ""; // Reset the input field
            }
        },
    },
};
</script>

<style scoped>
input {
    border: 3px solid #db922b;
    background-color: white;
    color: #35495e;
    border-radius: 0.5rem;
    padding: 0.5rem 1rem;
    font-size: 1rem;
    width: 50vw;
    transition: 0.1s ease-in-out;
}
input:focus-visible {
    border-color: rgb(215, 120, 69, 0.5);
    outline: none;
}

@media only screen and (max-width: 1024px) {
    input {
        width: 70vw;
    }
}
</style>
