<template>
    
    <nav class="navbar">
        <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/1/19/Spotify_logo_without_text.svg/2048px-Spotify_logo_without_text.svg.png" alt="">
    </nav>

</template>

<script>
export default {
    name: 'Header',
    data(){
        return {
            
        }
    }
}
</script>

<style lang="scss" scoped>
@import "../assets/scss/style.scss";
    nav {
        height: $header_height;
        background-color: $bg_header;
        img {
            height: 2.5em;
            margin-left: 0.7em;
        }
    }
</style>