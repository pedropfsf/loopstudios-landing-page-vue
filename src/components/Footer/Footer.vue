<template>
    <footer id="Footer">
        <div class="line">
            <img
                :src="require('../../assets/logo.svg')"
                alt="logo loopstudios"
            />

            <div id="area-social-media">
                <a 
                    class="link-social-media"
                    href="#"
                    v-for="item in iconsSocialMedia"
                    :key="item.id"
                >
                    <img
                        :src="require(`../../assets/${item.src}`)"
                        :alt="item.alt"
                    />
                </a>
            </div>
        </div>
        <div class="line">
            <nav id="nav-bar-footer">
                <ul id="list-items">
                    <li
                        class="item-text-link"
                        v-for="item in navBarFooterLinks"
                        :key="item.id"
                    >
                        <span class="text-link">
                            {{ item.text }}
                        </span>
                    </li>
                </ul>
            </nav>
        </div>
    </footer>
</template>

<script>

    export default {
        name: "Footer",
        components: {

        },
        data() {
            return {
                iconsSocialMedia: [
                    {
                        id: 1,
                        src: "icon-facebook.svg",
                        alt: "icon Facebook"
                    },
                    {
                        id: 2,
                        src: "icon-twitter.svg",
                        alt: "icon Twitter"
                    },
                    {
                        id: 3,
                        src: "icon-pinterest.svg",
                        alt: "icon Pinterest"
                    },
                    {
                        id: 4,
                        src: "icon-instagram.svg",
                        alt: "icon Instagram"
                    }
                ],
                navBarFooterLinks: [
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
            }
        }
    }

</script>

<style scoped>

    footer#Footer {
        width: 100%;
        height: 10rem;

        background-color: var(--black);
    
        flex-direction: column;

        justify-content: space-around;
    }

    a.link-social-media
    {
        justify-content: center;
    }

    footer#Footer,
    div.area-social-media,
    div.line,
    div#area-social-media,
    a.link-social-media,
    ul#list-items
    {
        display: flex;
        align-items: center;
    }

    div.line {
        width: 80%;

    }

    div.area-social-media,
    div.line,
    div#area-social-media,
    ul#list-items
    {
        justify-content: space-between;
    }

    div#area-social-media {
        width: 9rem;
    }

    li.item-text-link {
        list-style-type: none;
    }

    span.text-link {
        color: var(--white);

        font-family: Atala, Helvetica, sans-serif;
    }

</style>