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
    margin-top: 1.5em;
    width: 200px;
    border: none;
}
    
</style>