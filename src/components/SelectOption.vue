<template>

    <select  v-model="selected" @change="$emit('filter', selected)" name="" id="">
        <option value="all" selected>all</option>
        <option v-for="(element, index) in option" :key="index" :value="element">{{element}}</option>
    </select>

</template>

<script>
export default {  
    name: "Select",
    props: {
        option: Array
    },
    data() {
        return {
            selected: "all",
        }
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