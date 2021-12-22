<template>
    <div 
        id="ButtonMobile"
        @click="$emit('click-button')"
    >
        <div 
            class="line"
            :style="{ 
                top: lineTop.top, 
                transform: lineTop.transform
            }"
        >
        </div>
        <div 
            class="line"
            :style="{
                transform: lineCenter.transform
            }"
        >
        </div>
        <div 
            class="line"
            :style="{
                bottom: lineBottom.bottom,
                transform: lineBottom.transform
            }"
        >
        </div>
    </div>
</template>

<script>

    export default {
        name: "ButtonMobile",
        components: {

        },
        props: {
            value: {
                require: true,
                type: Boolean
            }
        },
        data() {
            return {
                lineTop: {
                    top: "0%",
                    transform: "",
                    },
                lineCenter: {
                    transform: "",

                },
                lineBottom: {
                    bottom: "0%",
                    transform: "",
                }
            }
        },
        methods: {
            changeStylesLine(value) {
                if(value) {
                    this.lineTop.top = "50%",
                    this.lineTop.transform = "rotate(45deg)";

                    this.lineCenter.transform = "rotate(45deg)",
                    
                    this.lineBottom.bottom = "50%",
                    this.lineBottom.transform = "rotate(-45deg)";
                } else {
                    this.lineTop.top = "0%",
                    this.lineTop.transform = "";

                    this.lineCenter.transform = "",
                    
                    this.lineBottom.bottom = "0%",
                    this.lineBottom.transform = "";
                }
            }
        },
        updated() {
            this.changeStylesLine(this.value);
        }
    }

</script>

<style scoped>
    div#ButtonMobile {
        width: 50px;
        height: 25px;

        display: flex;
        flex-direction: column;
        justify-content: space-between;
        align-items: center;

        margin-right: 7.5vw;
    }

    div#ButtonMobile > div.line {
        width: 45px;
        height: 2px;

        background-color: var(--white);

        position: relative;

        transition: all 200ms;
    }

</style>