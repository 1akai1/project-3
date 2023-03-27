<template>
    <main class="d-main-card">
        <div class="content">
            <div class="d-main-card__content">
                <div 
                class="d-main-card__card"  
                v-for="card, index in mainSection" 
                :key="index">
                    <nuxt-link 
                        :to="`post/${String(card?.url)}`" 
                        class="d-main-card__image none d-main-card__hover"  
                        :class="`id-${card?.category?.id}`" 
                        :style="`background-image: url(${card?.image?.url});`">
                        <div class="d-main-card__articles">
                            <p>{{card?.category?.name}}</p>
                            <time>
                                {{new Date(card?.updated_at).toLocaleString('ru', {day:'numeric', month:'long', year:'numeric'})}}
                            </time>
                        </div>
                        <div class="d-main-card__title hover">{{card?.title}}</div>
                    </nuxt-link>
                </div>
            </div>
        </div>
    </main>
</template>
<script setup>
    const props = defineProps({
        mainSection: Array
    })
    // console.log(props.mainSection)
</script>
<style lang="sass" scoped>
    .d-main-card
        &__content
            display: grid
            grid-template-columns: repeat(4, 1fr) 
            height: 500px
            gap: 3px

        &__card
            overflow: hidden
        &__image
            position: relative
            color: #fff
            background-position: center
            background-size: cover
            background-repeat: no-repeat
            display: flex
            flex-direction: column
            justify-content: space-between
            height: 100%
            transition: .2s ease-in-out
            -moz-transition: .2s ease-in-out
            -ms-transition: .2s ease-in-out
            -o-transition: .2s ease-in-out
            -webkit-transition: .2s ease-in-out
            -webkit-box-shadow: 0px 0px 20px -7px rgba(22, 28, 32, 0.57)
            -moz-box-shadow: 0px 0px 20px -7px rgba(22, 28, 32, 0.57)
            box-shadow: 0px 0px 20px -7px rgba(22, 28, 32, 0.57)
            &:hover 
                &::before
                    transform: scale(1.2)
                    box-shadow: -5px -200px 170px -56px rgba(241,50,77,1) inset
                    -webkit-box-shadow: -5px -200px 170px -56px rgba(241,50,77,1) inset
                    -moz-box-shadow: -5px -200px 170px -56px rgba(241,50,77,1) inset
            &:hover .hover
                transform: translate(0, -60%)

            &::before
                content: ''
                position: absolute
                background: inherit
                background-size: inherit
                height: 100%
                width: 100%
                transition: .2s ease-in-out
                -moz-transition: .2s ease-in-out
                -ms-transition: .2s ease-in-out
                -o-transition: .2s ease-in-out
                -webkit-transition: .2s ease-in-out
        &__articles
            position: relative
            display: flex
            flex-direction: row
            justify-content: space-between
            padding: 15px
        &__title
            padding: 15px
            position: relative
            transition: .2s ease-in-out
            -moz-transition: .2s ease-in-out
            -ms-transition: .2s ease-in-out
            -o-transition: .2s ease-in-out
            -webkit-transition: .2s ease-in-out
    .id-1
        &::before
            transition: .2s ease-in-out
            position: absolute
            content: ''
            width: 100%
            height: 100%
            box-shadow: -5px -200px 170px -114px #5fb992c7 inset
            -webkit-box-shadow: -5px -200px 170px -114px #5fb992c7 inset
            -moz-box-shadow: -5px -200px 170px -114px #5fb992c7 inset
    .id-2
        &::before
            transition: .2s ease-in-out
            position: absolute
            content: ''
            width: 100%
            height: 100%
            box-shadow: -5px -200px 170px -114px #8baa25c7 inset
            -webkit-box-shadow: -5px -200px 170px -114px #8baa25c7 inset
            -moz-box-shadow: -5px -200px 170px -114px #8baa25c7 inset
    .id-3
        &::before
            transition: .2s ease-in-out
            position: absolute
            content: ''
            width: 100%
            height: 100%
            box-shadow: -5px -200px 170px -114px rgba(170,164,37,0.78) inset
            -webkit-box-shadow: -5px -200px 170px -114px rgba(170,164,37,0.78) inset
            -moz-box-shadow: -5px -200px 170px -114px rgba(170,164,37,0.78) inset
    .id-4
        &::before
            transition: .2s ease-in-out
            position: absolute
            content: ''
            width: 100%
            height: 100%
            box-shadow: -5px -200px 170px -114px #3925aac7 inset
            -webkit-box-shadow: -5px -200px 170px -114px #3925aac7 inset
            -moz-box-shadow: -5px -200px 170px -114px #3925aac7 inset
    .id-5
        &::before
            transition: .2s ease-in-out
            position: absolute
            content: ''
            width: 100%
            height: 100%
            box-shadow: -5px -200px 170px -114px #aa259fc7 inset
            -webkit-box-shadow: -5px -200px 170px -114px #aa259fc7 inset
            -moz-box-shadow: -5px -200px 170px -114px #aa259fc7 inset
</style>