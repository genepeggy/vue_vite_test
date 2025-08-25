<!-- Vue2 -->
<!-- Person.vue -->
 
<!-- js或ts start -->

<!-- 拿來設定component名字 -->
<script lang="ts">
    export default{
        name:"person",
    }
</script>
<!-- 拿來設定compositionAPI -->
<script lang='ts' setup>
    //數據 
    let name = "Peggy"
    let age = 18
    let tel = "013"
    // 不需要寫return

     // 方法
    function changeName(){
        name="Peggy2"
        console.log(name);
        
    }
    function changeAge(){
        
        
        age=5
        console.log(age);
    }
    function showTel(){
        
        
        alert(tel)
        console.log(tel);
    }
</script>
<!-- js或ts end -->

<!-- html結構 start -->
<template>
    <div class="person">
        <!-- <h2>{{ a }}</h2> -->
        <h2>姓名:{{ name }}</h2>
        <h2>年齡:{{ age }}</h2>
        <button @click="changeName">修改名字</button>
        <button @click="changeAge">修改年齡</button>
        <button @click="showTel">顯示電話</button>
        <hr>

    </div>
</template>
<!-- html結構 end -->
<!-- 樣式 start -->
<style scoped>
    .person{
        background-color: skyblue;
        box-shadow: 0 0 10px;
        border-radius: 10px;
        padding: 20px;
    }
    button{
        margin-right: 10px;
    }
</style>
<!-- 樣式 end -->