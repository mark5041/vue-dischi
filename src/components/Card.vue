<template>

    <div class="card">
        <img :src="img" :alt="alt">
        <h1>{{title}}</h1>
        <span class="mt-2">{{author}}</span>
        <span class="pb-3">{{date}}</span>
    </div>

</template>

<script>
export default {  
    name: "Card",
    props: {
        img: {
            type: String,
        },
        alt: {
            type: String,
        },
        title: {
            type: String,
        },
        author: {
            type: String,
        },
        date: {
            type: String,
        },
        product: Object,
    },
    data() {
        return {

        }
    }
}
</script>

<style lang="scss" scoped>
@import "../assets/scss/style.scss";
    
    .card {
        flex-basis: $card_width;
        align-items: center;
        background-color: $bg_card;
        text-align: center;
        border-radius: 0;
        img {
            margin: 1.3em 0;
            width: 80%;
        }
        h1 {
            color: $title_color;
            font-size: $title_size;
            width: 80%;
            text-transform: uppercase;
        }
        span {
            color: $sub_title_color;
            font-size: $sub_title_size;
            line-height: calc($sub_title_size + 5px);
        }
    }
    
</style>