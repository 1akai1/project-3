<template>
    <div class="d-content-card content">
        <div 
        class="d-content-card__content" 
        v-for="contentBox in contentSection" 
        :key="contentBox">
            <nuxt-link 
            :to='contentBox?.url' 
            class="d-content-card__title none">
                    {{contentBox?.name}} ->
            </nuxt-link>
            <div 
            v-if="contentBox.articles.length !== 0" 
            class="d-content-card__box">
                <article 
                class="d-content-card__card" 
                v-for="itemCard in contentBox?.articles" 
                :key="itemCard">
                    <nuxt-link 
                    class="d-content-card__text" 
                    :to="`post/${itemCard.url}`">
                        <div class="d-content-card__card-box">
                            <div 
                                class="d-content-card__image" 
                                :style="`background-image: url(${itemCard?.image?.url});`" />
                            <div class="d-content-card__articles">
                                    <p class="d-content-card__title-articles">{{itemCard?.title}}</p>
                                    <div class="d-content-card__data" v-html='itemCard?.content'/>
                            </div>
                        </div>
                    </nuxt-link>
                </article>
            </div>
            <div v-else >Пока статей нет =(</div>
        </div>
    </div>
</template>
<script setup>
    const props = defineProps({
        contentSection: Array,
    })
        console.log(props.contentSection)

</script>
<style lang="sass">
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
            display: block
            &::after
                content: ''
                height: 3px
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
                -webkit-box-shadow: 0px 0px 20px -7px rgba(22, 28, 32, 0.351)
                -moz-box-shadow: 0px 0px 20px -7px rgba(22, 28, 32, 0.351)
                box-shadow: 0px 0px 20px -7px rgba(22, 28, 32, 0.351)
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
            color: #2c3e50
            text-decoration: none
            font-family: OpenSans,Arial,sans-serif 
        &__data
            h1
                text-decoration: none
                color: #000
                font-weight: normal
                font-size: .9rem
            a, p, h2, h3, strong
                text-decoration: none
                color: #2c3e50
                font-weight: lighter
                font-size: .9rem
            img
                display: none

</style>