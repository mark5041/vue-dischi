<template>

    <select  v-model="selected" @change="$emit('filter', selected)" name="" id="">
        <option value="all" selected>all</option>
        <option v-for="(element, index) in category" :key="index" :value="element">{{element}}</option>
    </select>

</template>

<script>
export default {  
    name: "Select",
    props: {
        option: Object
    },
    data() {
        return {
            objects: this.option,
            category: [],
            selected: "all"
        }
    },
    created() {
        this.objects.forEach(element => {
            if(!this.category.includes(element.genre))
            {
                this.category.push(element.genre);
            }
        });
    },
    methods: {

    }
}
</script>

<style lang="scss" scoped>
@import "../assets/scss/style.scss";
    
select {
    position: relative;
    left: 43.3%;
    top: 3%;
    width: 200px;
}
    
</style>