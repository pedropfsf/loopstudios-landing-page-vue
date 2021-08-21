<template>
    <main id="Main">
      <SectionFacts/>
      <AreaCards/>
    </main>
</template>

<script>

    import SectionFacts from './SectionFacts/SectionFacts.vue';
    import AreaCards from './AreaCards/AreaCards.vue';

    export default {
        name: "Main",
        components: {
            SectionFacts,
            AreaCards
        }
    }

</script>

<style scoped>
    main#Main {
        width: 80%;

        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
    }
</style>