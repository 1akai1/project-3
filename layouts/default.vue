<template>
    <div class="root">
        <DNavBar class="nav" :nav="data" />
        <DTagBar class="tag" :tag="tag" />
        <NuxtPage 
        class="wrap main-content" 
        :contentSection="contentSection" 
        :mainSection="mainSection"/>
        <DFooter />
    </div>
</template>

<script setup>
    const { data } = await useLazyFetch('https://adm.desync.ru/categories')
    const  articles  = await useLazyFetch('https://adm.desync.ru/articles?_sort=created_at:desc')
    let scroll = Number
    const tag = ['новость','патч', 'гайд', 'полезное', 'баг']
    const mainSection = []
    const contentSection = []


    data.value.forEach(element => {
        element.articles = element.articles.reverse()
        element.articles = element.articles.slice(0,6)
        contentSection.push(element)
    })

    articles.data.value.slice(0,8).forEach(element => {
        mainSection.push(element)
    })


    function sticky(){
        scroll = window.scrollY
        if (scroll > 0) {
            document.querySelector('.nav').classList.add('sticky')
            document.querySelector('.tag').classList.add('show')
        }
        else
            {
            document.querySelector('.nav').classList.remove('sticky')
            document.querySelector('.tag').classList.remove('show')
        }
    }

    onMounted(() => {
       window.addEventListener('scroll',sticky)
    })


    // console.log('articles')
    // console.log(nav)
</script>
    
<style lang="sass">
    @import '/assets/styles/styles.sass'
</style>