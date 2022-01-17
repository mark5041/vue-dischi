<template>
    
    <main>
        <div v-if="cards" class="container">
            <div class="row">
                <Card v-for="(element, index) in cards" :key="index"
                    :img="element.poster"
                    :alt="element.title"
                    :title="element.title"
                    :author="element.author"
                    :date="element.year"
                />
            </div>
        </div>
    </main>

</template>

<script>
import Card from './Card.vue'
import axios from 'axios'

export default {
  name: "Main",
	components: {
		Card,
	},
	data() {
		return {
			cards: null,
		}
	},
	mounted() {
		this.getCards();
	},
	methods: {
		getCards() {
			axios.get('https://flynn.boolean.careers/exercises/api/array/music')
			.then((result) => {
				this.cards = result.data.response;
			})
			.catch((error) => {
				console.log(error);
			})
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
            top: 6em;
            .row {
                column-gap: $card_gap;
                row-gap: calc($card_gap / 2);
            }
        }
    }
    
</style>