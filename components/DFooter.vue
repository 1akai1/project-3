<template lang="">
    <div class='d-footer'>
        <div class="d-footer__content content">
            <div class="d-footer__left">
                <div class="d-footer__logo">DeSync</div>
                <div class="d-footer__create">© 2018 - {{new Date().getFullYear()}}, DeSync.ru</div>
            </div>
            <div class="d-footer__right">
                <div class="d-footer__social">
                    <p>Ещё мы есть тут</p>
                    <div class="d-footer__social-box">
                        <img class="d-footer__image" src="../assets/image/vk.e4b267c.svg" alt="">
                        <img class="d-footer__image" src="../assets/image/telegram_cleared.624ccb0.svg" alt="">
                        <img class="d-footer__image" src="../assets/image/discord.f9b02c2.svg" alt="">
                    </div>
                </div>
                <div class="d-footer__boosty">
                    <p>А тут можно помочь</p>
                    <div class='d-footer__boosty-box'>
                        <img class="d-footer__image"  src="../assets/image/Boosty.svg" alt="">
                        <p class='d-footer__boosty-text'>boosty.to/erl</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    props:{
        footer: Array
    },
}
</script>
<style lang="sass">
.d-footer
    background-color: #000
    &__content
        display: flex
        flex-direction: row
        justify-content: space-between
        color: #fff
        padding: 20px
    &__left
        display: flex
        flex-direction: column
        justify-content: space-around
    &__right
        display: flex
        flex-direction: column
        padding: 4px
    &__image
        height: auto
        width: 30px
    &__social
        &-box
            display: flex
            flex-direction: row
            align-items: center
            justify-content: space-between
    &__boosty
        &-box
            display: flex
            flex-direction: row
            align-items: center
            justify-content: space-between
        &-text
            display: inline
        
</style>