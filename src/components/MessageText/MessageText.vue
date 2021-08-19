<template>
    <div id="MessageText">
        <span id="text">
            <slot>

            </slot>
        </span>
    </div>
</template>

<script>

    export default {
        name: "MessageText",
        components: {

        }
    }

</script>

<style scoped>
    div#MessageText {
        padding: 20px;

        width: 40rem;

        border: 2px solid var(--white);

        margin-bottom: 7.5vw;
        margin-left: 7.5vw;
    }

    span#text {
        color: var(--white);

        letter-spacing: 1px;

        font-family: "Josefin Sans";
        font-size: 70px;
    }

</style>