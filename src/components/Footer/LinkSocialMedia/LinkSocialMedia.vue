<template>
    <a 
        class="link-social-media"
        href="#"
    >
        <img
            :src="require(`../../../assets/${ src }`)"
            :alt="alt"
        />
    </a>
</template>

<script>

    export default {
        name: "LinkSocialMedia",
        components: {

        },
        props: {
            src: {
                require: true,
                type: String
            },
            alt: {
                require: true,
                type: String
            }
        }
    }

</script>

<style scoped>

    a.link-social-media {
        display: flex;
        align-items: center;
    }

</style>