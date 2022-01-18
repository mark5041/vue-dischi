<template>

    <select  name="" id="">
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
        }
    },
    mounted() {
        this.objects.forEach(element => {
            if(!this.category.includes(element.genre))
            {
                this-this.category.push(element.genre);
            }
        });
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