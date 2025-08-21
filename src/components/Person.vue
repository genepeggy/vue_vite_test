<!-- Vue2 -->
<!-- Person.vue -->
<!-- js或ts start -->
<script lang="ts">
    export default{

        setup(){
            
            // setup中不能寫this，this是undefined，在vue3中this被弱化了
            // data
            let name = "Peggy"
            let age = 18
            let tel = "013"
            // let x = d
            
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
            return{
                name:name,
                age:age,
                changeName,
                changeAge,
                showTel
            }
            // return返回值也可以是函式
            // return () => 'haha'
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
        <hr>
        <h2>測試:{{a}}</h2>
        <h2>測試:{{c}}</h2>
        <h2>測試:{{d}}</h2>
        <button @click="b">測試</button>
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