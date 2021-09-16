<template>
    <header id="Header">
        <img
            id="logo"
            src="../../assets/logo.svg"
            alt="logo image"
        />
        <nav 
            id="navBar"
            v-show="toggleMenu === 'desktop'"
        >
            <ul id="listItens">
                <Item
                    v-for="item in itemsNavBar"
                    :key="item.id"
                    :textLink="item.text"
                />
            </ul>
        </nav>
        <ButtonMobile 
            v-show="toggleMenu === 'mobile'"
            @click-button="methodMenuMobile"
            :value="valueMenuMobile"
        />
    </header>
</template>

<script>

    import Item from './Item/Item.vue';
    import ButtonMobile from './ButtonMobile/ButtonMobile.vue';

    export default {
        name: "Header",
        components: {
            Item,
            ButtonMobile,
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
                ],
                mediaQuerieList: matchMedia("(max-width: 822px)"),
                toggleMenu: "desktop"
            }
        },
        methods: {
            showButtonMobile(mediaQuerieList) {
                if(mediaQuerieList.matches) {
                    this.toggleMenu = "mobile";
                } else {
                    this.toggleMenu = "desktop";
                }
            },
        },
        mounted() {
            this.showButtonMobile(this.mediaQuerieList);

            this.mediaQuerieList.addEventListener('change', this.showButtonMobile);
        },
        props: {
            valueMenuMobile: {
                require: true,
                type: Boolean
            },
            methodMenuMobile: {
                require: true,
                type: Function
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

    @media screen and (max-width: 443px) {
        header#Header {
            height: 5.5rem;
        }

        img#logo {
            width: 7.5rem;
        }
    }

</style>