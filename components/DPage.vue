<template>
    <div class="container d-page">
        <h1 class="d-page__title">{{ contentPage[0].title }}</h1>
        <time class="d-page__date">{{ contentPage[0].updated_at }}</time>
        <img class="d-page__image" :src="contentPage[0].image.url" alt="">
        <div class="d-page__data" v-html="contentPage[0].content"/>
    </div>
</template>

<script setup>
    const props = defineProps({
        contentPage: Array
    })

    console.log(props.contentPage[0])
</script>

<style lang="sass">

    .container
        max-width: 900px
        margin: 0 auto
    .d-page
        &__image
            margin-top: 20px
            width: 100%
            height: auto
            border-radius: 5px
        &__title
            margin-bottom: 10px
            font-family: Oswald
            font-weight: 700
        &__date
            font-size: .9rem
        &__data
            font-family: OpenSans
            color: #2c3e50
            font-size: 16px
            img
                width: 100%
                height: auto
                border-radius: 5px
            strong
                font-weight: bold
            i
                font-style: italic
            p
                line-height: 1.6

</style>