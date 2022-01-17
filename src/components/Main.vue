<template>
    
    <main>
        <div class="container">
            <div class="row">
                <div class="card">
                    <img src="https://picsum.photos/id/684/600/400" alt="">
                    <h1>New Jersey</h1>
                    <h3>New Jersey</h3>
                </div>
            </div>
        </div>
    </main>

</template>

<script>
export default {
    name: 'Main',
    data(){
        return {
            
        }
    }
}
</script>

<style lang="scss" scoped>
@import "../assets/scss/style.scss";
    
    main {
        background-color: $bg_main;
        height: $main_height;
        width: 100%;

        .container{
            position: relative;
            top: 7em;
            .row {
                column-gap: $card_gap;
                row-gap: calc($card_gap / 2);
                .card {
                    flex-basis: $card_width;
                    align-items: center;
                    background-color: $bg_card;
                    img {
                        margin: 1em 0;
                        width: 80%;
                    }
                    h1 {
                        color: $title_color;
                        font-size: $title_size;
                    }
                    h3 {
                        color: $sub_title_color;
                        font-size: $sub_title_size;
                        margin-top: 1.5em;
                        margin-bottom: 1em;
                    }
                }
            }
        }
    }
    
</style>