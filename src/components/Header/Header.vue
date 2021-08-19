<template>
    <header id="Header">
        <img
            id="logo"
            src="../../assets/logo.svg"
            alt="logo image"
        />
        <nav id="navBar">
            <ul id="listItens">
                <Item
                    v-for="item in itemsNavBar"
                    :key="item.id"
                    :textLink="item.text"
                />
            </ul>
        </nav>
    </header>
</template>

<script>

    import Item from './Item/Item.vue';

    export default {
        name: "Header",
        components: {
            Item
        },
        data() {
            return {
                itemsNavBar: [
                    {
                        id: 1,
                        text: "About"
                    },
                    {
                        id: 2,
                        text: "Careers"
                    },
                    {
                        id: 3,
                        text: "Events"
                    },
                    {
                        id: 4,
                        text: "Products"
                    },
                    {
                        id: 5,
                        text: "Support"
                    }
                ]
            }
        }
    }

</script>

<style scoped>
    header#Header {
        width: 100%;
        height: 10rem;

        justify-content: space-between;
    }

    img#logo {
        margin-left: 7.5vw;
    }

    header#Header,
    nav#navBar,
    ul#listItens
    {
        display: flex;
        align-items: center;
    }

    nav#navBar {
        margin-right: 7.5vw;
    }

    ul#listItens {
        width: 30rem;

        justify-content: space-around;
    }

</style>