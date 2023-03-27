<template>
    <div>
        <DPage :content-page="data"/>
    </div>
</template>

<script setup>
    const { id } = useRoute().params
    const url = 'https://adm.desync.ru/articles?url=' + id
    const { data } = await useFetch(url)


    // console.log( data )
</script>

<style lang="sass" scoped>

</style>