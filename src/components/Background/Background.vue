<template>
    <div id="Background">
        <slot>

        </slot>
    </div>
</template>

<script>

    export default {
        name: "Background",
        components: {

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

        background-image: url(../../assets/desktop/image-hero.jpg);
        background-repeat: no-repeat;
        background-size: cover;
        background-position: center;
    }

</style>
