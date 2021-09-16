<template>
    <a 
        class="link-social-media"
        href="#"
        ref="link"
    >
        <div class="area-social-media">
            <img
                :src="require(`../../../assets/${ src }`)"
                :alt="alt"
            />
            <div 
                class="bar"
                ref="bar"
            ></div>
        </div>
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
        },
        mounted() {
            const linkRef = this.$refs.link;
            const barRef = this.$refs.bar;

            linkRef.addEventListener('mouseenter', () => {
                barRef.style.width = "100%";
            }, true)

            linkRef.addEventListener('mouseout', () => {
                barRef.style.width = "0px";
            }, true)
        }
    }

</script>

<style scoped>

    div.area-social-media {
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        align-items: center;
    }

    div.bar {
        width: 0;
        height: 3px;

        background-color: var(--white);

        margin-top: 5px;

        transition: width 200ms;
    }

</style>