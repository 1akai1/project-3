<template>
    <div>
        <DContentCard :contentSection="contentSection" />
    </div>
</template>

<script setup>
    const { id } = useRoute().params
    const contentSection = []
    const url = 'https://adm.desync.ru/categories?url=' + id
    const { data } = await useFetch(url)


    contentSection.push(data.value[0])

    // console.log(contentSection)
</script>

<style lang="sass" scoped>

</style>