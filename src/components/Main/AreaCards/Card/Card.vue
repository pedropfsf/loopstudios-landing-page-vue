<template>
    <li class="itemCard">
        <div 
            class="Card"
            :style="{
                backgroundImage: `url(${require(`../../../../assets/${typeSource}/${src}`)})`
            }"
        >
            
            <span class="textCard">
                {{ text }}
            </span>
        </div>
    </li>
</template>

<script>

    export default {
        name: "Card",
        components: {

        },
        props: {
            src: {
                require: true,
                type: String
            },
            text: {
                require: true,
                type: String
            },
        },
        data() {
            return {
                typeSource: "desktop",
                mediaQuerieList: matchMedia("(max-width: 984px)"),
            }
        },
        methods: {
            toggleTypeSource(mediaQuerieList) {
                if(mediaQuerieList.matches) {
                    this.typeSource = "mobile";
                } else {
                    this.typeSource = "desktop";
                }
            }
        },
        mounted() {
            this.toggleTypeSource(this.mediaQuerieList);

            this.mediaQuerieList.addEventListener('change', this.toggleTypeSource);
        }
    }

</script>

<style scoped>

    li.itemCard {
        list-style-type: none;

        margin-right: 15px;
        margin-bottom: 15px;
    }

    li.itemCard:nth-of-type(4),
    li.itemCard:nth-of-type(8)
    {
        margin-right: 0;
    }


    div.Card {
        height: 27.5rem;

        padding: 20px;

        background-repeat: no-repeat;
        background-position: center;

        display: flex;
        flex-direction: column;
        justify-content: flex-end;
        align-items: flex-start;
    }

    img.imageCard {
        position: absolute;
    }

    span.textCard {
        color: var(--white);

        font-family: "Josefin Sans";
        font-size: 30px;
    }

    @media screen and (max-width: 984px) {
        li.itemCard {
            margin-right: 0;

        }

        li.itemCard,
        div.Card
        {
            width: 100%;
        }

        div.Card {
            height: 10rem;

            background-size: cover;

            padding: 20px;
        }
    }

</style>