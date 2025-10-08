<!-- Vue2 -->
<!-- Person.vue -->

<!-- js或ts start -->

<!-- 拿來設定component名字 -->
<!-- <script lang="ts">
    export default{
        name:"person",
    }
</script> -->
<!-- 拿來設定compositionAPI -->
<script lang='ts' setup>
    //物件用reactive 
    import { reactive } from 'vue';

    // 數據
    let car = reactive({brand:'BMW',price:100})
    console.log(car);
    // 結果:Proxy(Object) {brand: 'BMW', price: 100}
    // let car={brand:'BMW',price:100}
    // console.log(car);
    // 結果:{brand: 'BMW', price: 100}
    // console.log(Proxy);
    // js原生的內建函數
    let games = reactive([
        {id:'game01',name:'genshin'},
        {id:'game02',name:'star rail'},
        {id:'game03',name:'project sekai'},
    ])

    let obj = reactive({
        a:{
            b:{
                c:666
            }
        }
    })
    

    // 方法
    function changePrice(){
        car.price += 10
        console.log(car.price);
        
    }
    function changeFirstGameName(){
        games[0].name="原神 空月之歌"
    }
    function changeObj(){
        obj.a.b.c=999
    }
</script>
<!-- js或ts end -->

<!-- html結構 start -->
<template>
    <div class="person">
        <h2>汽車資訊:一輛{{car.brand}}，價值{{car.price}}萬</h2>
        <button @click="changePrice">修改價格</button>
        <br>
        <h2>遊戲列表</h2>
        <ul>
            <!-- <li>{{games[0].name}}</li>
            <li>{{games[1].name}}</li>
            <li>{{games[2].name}}</li> -->
            <!-- vue的特殊寫法:遍歷每個在物件中的元素 -->
            <li v-for="item in games" :key="item.id">{{ item.name }}</li>
        </ul>
        <button @click="changeFirstGameName">修改第一個遊戲的名字</button>
        <hr>
        <h2>測試:{{obj.a.b.c}}</h2>
        <button @click="changeObj">測試修改obj</button>
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
    li{
        font-size: 1.25rem;
    }
</style>
<!-- 樣式 end -->