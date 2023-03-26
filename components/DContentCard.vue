<template>
    <div class="d-content-card content">
        <div class="d-content-card__content" v-for="contentBox in contentSection" :key="contentBox">
            <nuxt-link :to='contentBox?.name' class="d-content-card__title none">
                {{contentBox?.name}} ->
            </nuxt-link>
            <div class="d-content-card__box">
                <article v-for="itemCard, index in contentBox?.articles" :key="index">
                    <div class="d-content-card__card">
                        <div class="d-content-card__image" :style="`background-image: url(${itemCard?.image?.url});`" />
                        <div class="d-content-card__articles">
                            <p class="d-content-card__title-articles">{{itemCard?.title}}</p>
                            <div class="d-content-card__text" v-html='itemCard?.content'/>
                        </div>
                    </div>
                </article>
            </div>
        </div>
    </div>
</template>
<script setup>
    const props = defineProps({
        contentSection: Array,
    })
</script>
<style lang="sass" scoped>
    .d-content-card
        &__title
            margin-top: 20px
            margin-bottom: 5px
        &__content
            display: flex
            flex-direction: column
        &__box
            display: flex
            flex-wrap: wrap
            gap: 20px
        &__card
            min-width: 250px
            max-width: 250px
            height: 300px
            overflow: hidden
            border-radius: 5px
            -webkit-box-shadow: 0px 0px 20px -7px rgba(22, 28, 32, 0.57)
            -moz-box-shadow: 0px 0px 20px -7px rgba(22, 28, 32, 0.57)
            box-shadow: 0px 0px 20px -7px rgba(22, 28, 32, 0.57)
        &__image
            width: 250px
            height: 145px
            background-position: center
            background-size: cover
        &__articles
            padding: 5px 10px
            font-size: 1rem
            background-color: #fff
            height: 100%
        &__text
            font-size: .9rem
            font-family: OpenSans,Arial,sans-serif
            font-weight: 200
            text-decoration: none
</style>