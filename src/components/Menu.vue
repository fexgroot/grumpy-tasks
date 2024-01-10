    <template>
    <div class="container">
        <button @click="handleClick">
        <img src="../assets/menu.svg" alt="Menu" />
        </button>
        <div class="menuList" :class="{ visible: showMenu }">
        <p>Idsdifjsdiuf 1</p>
        <p>sdfjhsdkfhsk 2</p>
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
        handleClick() {
        this.showMenu = !this.showMenu;
        },
    },
    };
    </script>

    <style scoped>
    .container {
    position: absolute;
    top: 2rem;
    left: 2rem;
    width: 15vw;
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
    border-radius: 15px;
    visibility: hidden;
    opacity: 0;
    box-shadow: 0 0 20px rgba(0, 0, 0, .1);
    transition: all 0.2s ease-in-out;
    }

    .visible {
    visibility: visible;
    opacity: 1;
    left: -1rem;
    }

    button {
    background: none;
    border: none;
    margin: 0;
    padding: 0;
    transition: 0.1s ease-in-out;
    position: absolute;
    z-index: 1;
    }

    button:hover {
    opacity: 0.8;
    cursor: pointer;
    }

    button:focus-visible {
    outline: none;
    opacity: 0.5;
    }
    </style>
