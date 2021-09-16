<template>
    <div id="MenuMobile">
        <nav id="nav">
            <ul id="list-items">
                <li
                    class="item"
                    v-for="item in items"
                    :key="item.id"
                >
                    <a 
                        class="link"
                        href="#"
                    >
                        {{ item.name }}
                    </a>
                </li>
            </ul>
        </nav>
    </div>
</template>

<script>
    export default {
        name: "MenuMobile",
        components: {

        },
        data() {
            return {
                items: [
                    {
                        id: 1,
                        name: "ABOUT"
                    },
                    {
                        id: 2,
                        name: "CAREERS"
                    },
                    {
                        id: 3,
                        name: "EVENTS"
                    },
                    {
                        id: 4,
                        name: "PRODUCTS"
                    },
                    {
                        id: 5,
                        name: "SUPPORT"
                    }
                ]
            }
        }
    }
</script>

<style scoped>
    div#MenuMobile {
        width: 100%;
        flex: 1;

        background-color: var(--black);
    }

    nav#nav {
        margin-left: 2rem;
    }

    div#MenuMobile,
    ul#list-items
    {
        display: flex;
        flex-direction: column;
        justify-content: center;
    }

    li.item {
        margin: 10px 0;
    }

    a.link {
        color: var(--dark-gray);

        font-size: 1.5rem;

        text-decoration: none;
    }
</style>