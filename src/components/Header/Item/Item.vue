<template>
    <li class="Item">
        <div class="area-item">
            <a class="link-item" href="#">
                {{ textLink }}
            </a>
            <div class="bar"></div>
        </div>
    </li>
</template>

<script>
    
    export default {
        name: "Item",
        components: {

        },
        props: {
            textLink: {
                required: true,
                type: String
            }
        }
    }

</script>

<style scoped>
    li.Item {
        list-style-type: none;
    }

    div.area-item {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;

    }

    a.link-item {
        color: var(--white);

        text-decoration: none;
        
        font-family: "Josefin Sans";
        font-weight: bold;
    }

    div.bar {
        width: 0;
        height: 3px;

        transition: width 200ms;

        margin-top: 10px;

        background-color: var(--white);
    }

    div.area-item:hover > div.bar {
        width: 100%;
    }
</style>