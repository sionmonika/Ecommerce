<template>
    <article class="each_promotion" :style="{ backgroundColor: bgColor}">
        <div class="content" >
            <h3>{{ content }}</h3>
            <Button_Component :shopNow="shopnow" :promotion="{ content }" :buttonColor="btnColor" />
        </div>
         
        <img :src= "`http://localhost:3000/`+ imageSrc" alt="Promotion image">
    </article>
</template>

<script>
import Button_Component from './Button_Component.vue';

export default {
    name: "Promotion",

    props: {
        content: String,
        imageSrc: String,
        bgColor: String,
        btnColor: String
    },

    components: {
        Button_Component,
    },

    methods: {
        shopnow(promotion) {
            alert("Let's shop " + promotion.content);
        },
    },
}
</script>

<style>
.each_promotion {
    display: flex;
    width: 27rem;
    position: relative;
    height: 14rem;
    align-items: center;
    padding-left: 2rem;
    border-radius: .25rem;
}
.each_promotion img {
    width: 22rem;
    height: 100%;
    position: absolute;
    right: 0;
}
.content {
    z-index: 1;
    display: flex;
    flex-direction: column;
    gap: 1rem;
    width: 50%;
}
</style>
