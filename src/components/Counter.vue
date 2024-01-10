<template>
    <div v-if="taskCount >= 10">
        <p v-if="taskCount < 25">Woah, you have {{ taskCount }} tasks! 😸</p>
        <p v-else-if="taskCount < 50">
            Woah, you have {{ taskCount }} tasks! 🙀
        </p>
        <p v-else>Thanks for using the app! 😻</p>
    </div>
</template>

<script>
export default {
    props: {
        taskCount: {
            type: Number,
            required: true,
        },
    },
};
</script>

<style scoped>
div {
    position: fixed;
    text-align: center;
    top: 1rem;
    right: 1rem;
    padding: 0rem 2rem;
    background-color: white;
    border-radius: 0.8rem;
    font-size: 1.1rem;
    font-weight: bold;
    box-shadow: 0 0 1rem rgb(53, 73, 94, 0.1);
}

p {
    display: flex;
    align-items: center;
}

img {
    width: 1.2rem;
}

@media only screen and (max-width: 1024px) {
    div {
        display: none;
    }
}
</style>
