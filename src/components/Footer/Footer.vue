<template>
    <footer id="Footer">
        <div id="side-bar-two-sides">
            <img
                id="logo-footer"
                :src="require('../../assets/logo.svg')"
                alt="logo loopstudios"
            />

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
            <div id="area-social-media">
                <li 
                    class="item-link-social-media"
                    v-for="item in iconsSocialMedia"
                    :key="item.id"
                >
                    <LinkSocialMedia
                        
                        :src="item.src"
                        :alt="item.alt"
                    />
                </li>
            </div>

            <span id="rights-text">
                © 2021 Loopstudios. All rights reserved.
            </span>

        </div>
    </footer>
</template>

<script>

    import LinkSocialMedia from './LinkSocialMedia/LinkSocialMedia.vue';

    export default {
        name: "Footer",
        components: {
            LinkSocialMedia
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
        height: 8rem;

        background-color: var(--black);

        justify-content: center;
    }

    div#side-bar-two-sides {
        width: 80%;
        height: inherit;

        display: grid;
        grid-template-areas: 
            "logo areaSocialMedia"
            "navBar rights"
        ;
    }

    nav#nav-bar-footer {
        grid-area: navBar;
        justify-self: flex-start;
    }

    img#logo-footer,
    div#area-social-media,
    nav#nav-bar-footer,
    span#rights-text
    {
        align-self: center;
    }

    img#logo-footer {
        grid-area: logo;
        justify-self: flex-start;
    }

    div#area-social-media {
        width: 9rem;

        grid-area: areaSocialMedia;
        justify-self: flex-end;
    }

    footer#Footer,
    div#area-social-media,
    ul#list-items 
    {
        display: flex;
    }

    div#area-social-media,
    ul#list-items 
    {
        justify-content: space-between;
        align-items: center;
    }

    ul#list-items {
        width: 30vw;
    }

    li {
        list-style-type: none;
    }

    a.link-social-media {
        justify-content: center;
    }

    span.text-link {
        color: var(--white);

        font-family: "Josefin Sans", Helvetica, sans-serif;
        font-weight: bold;
    }

    span#rights-text {
        color: var(--very-dark-gray);

        font-family: "Josefin Sans";
        font-size: 12.5px;
        font-weight: bold;

        grid-area: rights;
        justify-self: flex-end;
    }

    @media screen and (max-width: 1078px) {
        li.item-text-link {
            margin-right: 10px;
        }

        li.item-text-link:last-of-type {
            margin-right: 0;
        }
    }

    @media screen and (max-width: 818px) {
        footer#Footer {
            height: 25rem;
        }

        div#side-bar-two-sides {
            display: flex;
            flex-direction: column;
            justify-content: space-evenly;
            align-items: center;
        }

        ul#list-items {
            flex-direction: column;

            height: 10rem;
        }

        li.item-text-link {
            margin-right: 0;
        }

        span#rights-text {
            font-size: 20px;
        }
    }

    @media screen and (max-width: 450px) {
        span#rights-text {
            font-size: 15px;
        }
    }

</style>