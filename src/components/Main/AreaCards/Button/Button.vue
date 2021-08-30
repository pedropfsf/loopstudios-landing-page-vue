<template>
    <button id="Button">
        <span id="textButton">
            <slot>

            </slot>
        </span>
    </button>    
</template>

<script>

    export default {
        name: "Button",
        components: {

        }
    }

</script>

<style scoped>
    button#Button {
        display: flex;
        justify-content: center;
        align-items: center;

        background-color: var(--white);

        border-radius: 1px;

        padding: 10px 40px;
    }

    button#Button,
    span#textButton
    {
        transition: all 200ms;
    }

    button#Button:hover {
        background-color: var(--black);
    }

    button#Button:hover > span#textButton {
        color: var(--white);
    }

    span#textButton {
        font-family: "Josefin Sans";

        text-transform: uppercase;

        font-weight: bold;
    }

</style>