<template>
    <li class="Item">
        <a class="link-item" href="#">
            {{ textLink }}
        </a>
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

    a.link-item {
        color: var(--white);

        text-decoration: none;
        
        font-family: "Josefin Sans";
        font-weight: bold;
    }
</style>