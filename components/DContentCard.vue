<template>
    <div class="d-content-card content">
        <div class="d-content-card__content" v-for="contentBox in contentSection" :key="contentBox">
            <nuxt-link :to='contentBox?.url' class="d-content-card__title none">
                {{contentBox?.name}} ->
            </nuxt-link>
            <div class="d-content-card__box">
                <article class="d-content-card__card" v-for="itemCard, index in contentBox?.articles" :key="index">
                    <div class="d-content-card__card-box">
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
        // console.log(props.contentSection)

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
            position: relative
            &::after
                content: ''
                height: 100%
                width: 100%
                position: absolute
                bottom: 0
            &:hover
                &::after
                    -webkit-box-shadow: 0px -7px 0px -5px rgba(255, 0, 0, 1) inset
                    -moz-box-shadow: 0px -7px 0px -5px rgba(255, 0, 0, 1) inset
                    box-shadow: 0px -7px 0px -5px rgba(255, 0, 0, 1) inset
            &-box
                min-width: 250px
                max-width: 250px
                height: 300px
                overflow: hidden
                border-radius: 5px
                -webkit-box-shadow: 0px 0px 20px -7px rgba(22, 28, 32, 0.57)
                -moz-box-shadow: 0px 0px 20px -7px rgba(22, 28, 32, 0.57)
                box-shadow: 0px 0px 20px -7px rgba(22, 28, 32, 0.57)
                overflow: hidden
            &:hover .d-content-card__image
                height: 100px
        &__image
            width: 250px
            height: 145px
            background-position: 50%
            background-size: cover
            transition: .2s ease-in-out
        &__articles
            padding: 5px 10px
            font-size: 1rem
            background-color: #fff
            height: 100%
        &__text
            font-size: .9rem !important
            font-family: OpenSans,Arial,sans-serif 
            font-weight: 200 !important
            text-decoration: none !important
</style>