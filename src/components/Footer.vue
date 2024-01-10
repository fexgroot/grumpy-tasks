<template>
    <div>
        <p>
            Made with
            <a href="https://vuejs.org/" target="_blank" rel="noopener"
                >Vue.js</a
            >
        </p>
    </div>
</template>

<style scoped>
div {
    position: fixed;
    bottom: 0;
    width: 20%;
    margin-bottom: 1rem;
    text-align: center;
    font-weight: bold;
    border-radius: 0.8rem;
    background-color: rgb(52, 73, 94, 0.1);
    backdrop-filter: blur(5px);
    box-shadow: 0 0 1rem rgb(53, 73, 94, 0.1);
}

a {
    color: #42b883;
    text-decoration: none;
    font-weight: 900;
    transition: 0.1s ease-in-out;
}
a:hover {
    opacity: 0.7;
}
a:focus-visible {
    outline: none;
    opacity: 0.5;
}

@media only screen and (max-width: 1024px) {
    div {
        width: 100%;
        border-radius: 0;
        margin-bottom: 0;
    }
}
</style>
