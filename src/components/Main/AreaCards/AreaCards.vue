<template>
    <div id="AreaCards">
        <header id="headerCards">
            <span id="title">
                OUR CREATIONS
            </span>
            <Button>
                See All
            </Button>
        </header>
        <ul id="cards">
            <Card
                v-for="item in dataCard"
                :key="item.id"
                :src="item.src"
                :text="item.text"
            />
        </ul>
    </div>
</template>

<script>
    
    import Button from './Button/Button.vue';
    import Card from './Card/Card.vue';

    export default {
        name: "AreaCards",
        components: {
            Button,
            Card
        },
        data() {
            return {
                dataCard: [
                    {
                        id: 1,
                        src: "image-deep-earth.jpg",
                        text: "DEEP EARTH"
                    },
                    {
                        id: 2,
                        src: "image-night-arcade.jpg",
                        text: "NIGHT ARCADE"
                    },
                    {
                        id: 3,
                        src: "image-soccer-team.jpg",
                        text: "SOCCER TEAM VR"
                    },
                    {
                        id: 4,
                        src: "image-grid.jpg",
                        text: "THE GRID"
                    },
                    {
                        id: 5,
                        src: "image-from-above.jpg",
                        text: "FROM UP ABOVE VR"
                    },
                    {
                        id: 6,
                        src: "image-pocket-borealis.jpg",
                        text: "POCKET BOREALIS"
                    },
                    {
                        id: 7,
                        src: "image-curiosity.jpg",
                        text: "THE CURIOSITY"
                    },
                    {
                        id: 8,
                        src: "image-fisheye.jpg",
                        text: "MAKE IT FISHEYE"
                    }
                ]
            }
        }
    }

</script>

<style scoped>

    div#AreaCards {
        margin: 7rem 0;

        flex-direction: column;
        justify-content: center;
    }
    
    div#AreaCards,
    header#headerCards
    {
        width: 100%;

        display: flex;
        align-items: center;
    }

    header#headerCards {
        justify-content: space-between;

        margin-bottom: 60px;
    }

    span#title {
        font-family: "Josefin Sans";
        font-size: 2.5rem;
    }

    ul#cards {
        display: grid;
        grid-template: auto auto / 25% 25% 25% 25%;

        width: 100%;
    }

</style>