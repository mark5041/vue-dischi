<template>
    
    <main>
        <Select 
            :option="CompleteAlbums"
            @filter="GenreSelection($event)"
        />
        <div class="my-container">
            <div class="row">
                <Card v-for="(element, index) in filteredAlbums" :key="index"
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
import Select from './SelectOption.vue'
import axios from 'axios'

export default {
  name: "Main",
	components: {
		Card,
        Select
	},
	data() {
		return {
			CompleteAlbums: null,
            filteredAlbums: null,
            selected: "all"
		}
	},
	mounted() {
		this.getCards();
	},
    computed() {
        
    },
	methods: {
		getCards() {
			axios.get('https://flynn.boolean.careers/exercises/api/array/music')
			.then((result) => {
				this.CompleteAlbums = result.data.response;
                this.filteredAlbums = this.CompleteAlbums;
			})
			.catch((error) => {
				console.log(error);
			})
		},
       GenreSelection(selected) {
            this.selected = selected;
            if (this.selected == "" || this.selected == "all") 
            {
                this.filteredAlbums = this.CompleteAlbums;
            } 
            else 
            {
                this.filteredAlbums = this.CompleteAlbums.filter((element) => {
                    return element.genre == this.selected;
                });
            }
        },
    },
}
</script>

<style lang="scss" scoped>
@import "../assets/scss/style.scss";
    
    main {
        background-color: $bg_main;
        height: $main_height;
        width: 100%;

        .my-container{
            margin: 0 15%;
            .row {
                position: relative;
                top: 3.5em;
                height: 100%;
                column-gap: $card_gap;
                row-gap: calc($card_gap / 2);
            }
        }
    }
    
</style>