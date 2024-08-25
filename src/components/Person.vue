<template>
  <div class="person">
    <div>name: {{ person.name }}</div>
    <div>age: {{ person.age }}</div>
    <div>car name: {{ person.car.name }} car price:{{ person.car.price }}</div>
  </div> 
  <button @click="changeName">change name</button> 
  <button @click="changeAge">change age</button> 
  <button @click="changeCarName">change car name</button> 
  <button @click="changeCarPrice">change car price</button> 
  <button @click="changeWhole">change all car</button> 
  <hr>
</template>
<!-- install vue plugin fsr set up :this is not define vue component name -->
 <!--npm i vite-plugin-vue-setup-extend -D  -->
 <!--then config the vite.config.ts  -->
<script setup name="Person223">
// structure data still is reactive data by wrapper toRefs
import { watch, reactive } from 'vue';
let person = reactive({
  name:'Jolhe',
  age:12,
  car:{
    name:'大众',
    price:2222
  }
});
function changeName() {
  person.name += "~";
}
function changeAge() {
  person.age += 1;
}

function changeCarName(){
  person.car.name="雅迪"
}
function changeCarPrice(){
  person.car.price=666

}
function changeWhole(){
  person.car={
    name:'奥迪',
    price:222
  }
}
// 监听对象的某一个特定的值，需要用函数式写法来进行监听，确保不会被其他属性污染
watch(( )=>person.name,(newValue,oldValue)=>console.log("person change ",newValue,oldValue))
// 监听对象中的某个对象，也需要写函数式确保当前对象可以被监听到，如果需要监听对象内部属性，需要给监听一个deep 属性
watch(()=>person.car,(newValue,oldValue)=>console.log('car cahnge ',newValue,oldValue),{deep:true})
</script>
<style scoped>
.person{
    background-color: aliceblue;
    box-shadow: 0 0 10px;
    border-radius: 20px;
    padding: 20px;
}
.button{
    margin: 0px 5px;
}
</style>
