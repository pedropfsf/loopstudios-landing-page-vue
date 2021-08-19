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

        width: 50vw;

        border: 2px solid var(--white);

        margin-bottom: 7.5vw;
        margin-left: 7.5vw;
    }

    span#text {
        color: var(--white);

        letter-spacing: 1px;

        font-family: "Josefin Sans";
        font-size: 5.5vw;
    }

    @media screen and (max-width: 822px) {
        div#MessageText {
            margin-left: 0;
            margin-bottom: 8rem;

            width: 70vw;
        }

        span#text {
            font-size: 8vw;
        }
    }

    @media screen and (max-width: 498px) {
        div#MessageText {
            margin-bottom: 12rem;

            width: 80vw;
        }
    }

</style>