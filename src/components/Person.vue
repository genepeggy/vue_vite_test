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
    // ref可以定義基本類型數據、也可以定義對象類型數據
    import { reactive, ref } from 'vue';

    // 數據
    let car = ref({brand:'BMW',price:100})
    // console.log(car);
    // 結果:Proxy(Object) {brand: 'BMW', price: 100}
    // let car={brand:'BMW',price:100}
    // console.log(car);
    // 結果:{brand: 'BMW', price: 100}
    // console.log(Proxy);
    // js原生的內建函數
    let games = ref([
        {id:'game01',name:'genshin'},
        {id:'game02',name:'star rail'},
        {id:'game03',name:'project sekai'},
    ])
    let obj=reactive({x:999})

    console.log(car);

    console.log(obj);
    // 結果:RefIml(
    // value->是一個Proxy->用reactive定義
    // )
    // 因為RefIml最外層是用ref定義，所以也可以解釋成ref可以用來定義對象類型數據(實際上是RefIml內的value是一個Proxy在運作，不是外層的RefIml在運作)
    // ->同理可證也適用深層次數據(巢狀)
    // 方法
    function changePrice(){
        car.value.price += 10
        console.log(car.value.price);
        
    }
    function changeFirstGameName(){
        games.value[0].name="原神 空月之歌"
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