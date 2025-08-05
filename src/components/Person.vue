<!-- Vue2 -->
<!-- Person.vue -->
<!-- js或ts start -->
<script lang="ts">
    export default{
        name:'Person', //元件名
        
        setup(){
            // setup中不能寫this，this是undefined
            // data
            let name = "Peggy"
            let age = 18
            let tel = "013"
            
            // 方法
            function changeName(){
                console.log(1);
                
                name="Peggy2"
            }
            function changeAge(){
                console.log(2);
                
                age=5
            }
            function showTel(){
                console.log(3);
                
                alert(tel)
            }
            return{
                name:name,
                age:age,
                changeName,
                changeAge,
                showTel
            }
        }
    }
</script>
<!-- js或ts end -->
<!-- html結構 start -->
<template>
    <div class="person">
        <h2>姓名:{{ name }}</h2>
        <h2>年齡:{{ age }}</h2>
        <button @click="changeName">修改名字</button>
        <button @click="changeAge">修改年齡</button>
        <button @click="showTel">顯示電話</button>
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