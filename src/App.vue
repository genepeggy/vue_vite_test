<!-- Vue2 -->
<!-- App.vue -->
<!-- js或ts start -->
<script lang="ts">
    import Person from './components/Person.vue';
    export default{
        name:'App', //元件名
        components:{
            Person
        }
    }
</script>
<!-- js或ts end -->
<!-- html結構 start -->
<template>
    
        <!-- vue3可以有多個物件標籤，vue2則不可 -->
        <!-- <Person></Person>
        <Person></Person>
        <Person></Person> -->
        <Person></Person>
    
</template>
<!-- html結構 end -->
<!-- 樣式 start -->
<style scoped>
    .app{
        background-color: #ddd;
        box-shadow: 0 0 10px;
        border-radius: 10px;
        padding: 20px;
    }
</style>
<!-- 樣式 end -->