<template>
    <div class="content">
        <DMainCard :mainSection="mainSection" />
        <DContentCard :contentSection="contentSection" />
    </div>
</template>

<script setup>
    const props = defineProps({
        mainSection: Array,
        contentSection: Array,
    })
</script>

<style lang="sass" scoped>

</style>