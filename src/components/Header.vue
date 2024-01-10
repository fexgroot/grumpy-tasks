<template>
    <a href="../../index.html">😾</a>
    <h1>Grumpy Tasks</h1>
</template>

<script>
export default {
    name: "HeaderComponent",
};
</script>

<style scoped>
a {
    font-size: 3.5rem;
    text-shadow: 0 0.2rem rgb(53, 73, 94);
    text-decoration: none;
    font-weight: bold;
    transition: 0.1s ease-in-out;
}
a:hover {
    text-shadow: 0 -0.2rem rgb(53, 73, 94);
}
a:focus-visible {
    outline: none;
    opacity: 0.5;
}
h1 {
    font-size: 2.2rem;
    font-weight: 900;
    margin: 1.2em 0;
    margin-top: 0.4em;
}

@media only screen and (max-width: 1024px) {
    a {
        font-size: 3rem;
    }
    h1 {
        font-size: 1.8rem;
    }
}
</style>
