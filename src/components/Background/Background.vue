<template>
    <div 
        id="Background"
        ref="background"
    >
        <slot>

        </slot>
    </div>
</template>

<script>

    export default {
        name: "Background",
        components: {

        },
        props: {
            typeJustifyContent: {
                require: true,
                type: String
            },
            removeBackgroundImage: {
                require: true,
                type: Boolean
            }
        },
        updated() {
            this.$refs.background.style.justifyContent = this.typeJustifyContent;

            if(this.removeBackgroundImage) {
                this.$refs.background.style.backgroundImage = "none";
                this.$refs.background.style.height = "100vh";
            } else {
                this.$refs.background.style.backgroundImage = `url(${require('../../assets/desktop/image-hero.jpg')})`;
                this.$refs.background.style.height = "";
            }
        }
    }

</script>

<style scoped>

    div#Background {
        width: 100%;
        height: 45vw;

        display: flex;
        flex-direction: column;
        justify-content: space-between;
        align-items: flex-start;

        background-color: var(--black);
        background-image: url(../../assets/desktop/image-hero.jpg);
        background-repeat: no-repeat;
        background-size: cover;
        background-position: top;
    }

    @media screen and (max-width: 822px) {
        div#Background {
            align-items: center;

            background-image: url(../../assets/mobile/image-hero.jpg);

            height: 35rem;
        }
    }

</style>
