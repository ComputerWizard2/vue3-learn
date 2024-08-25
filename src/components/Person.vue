<template>
  <div class="person">
    <div>name: {{ person.name }}</div>
    <div>age: {{ person.age }}</div>
  </div> 
  <button @click="changeName">change Name</button> 
  <button @click="changePerson">change Person</button> 
  <hr>
  <div>{{ obj.a.b.c }}</div>
  <button @click="changeDeepProp">change deep prop</button>
</template>
<!-- install vue plugin fsr set up :this is not define vue component name -->
 <!--npm i vite-plugin-vue-setup-extend -D  -->
 <!--then config the vite.config.ts  -->
<script setup name="Person223">
// structure data still is reactive data by wrapper toRefs
import { watch, reactive } from 'vue';
let person = reactive({
  name:'Jolhe',
  age:12
});
let obj = reactive({a:{b:{c:666}}})
function changeName() {
  person.name += "~";
}
function changePerson(){
  person=Object.assign(person,{name:'Marry', age :22})
}
function changeDeepProp(){
  obj.a.b.c=888
}

watch(person, (newValue, oldValue) => {
  console.log(`new value: ${JSON.stringify(newValue)}, old value: ${JSON.stringify(oldValue)}`);
} );

// Implicit listening that force to open and not close
watch(obj,(newValue,oldValue)=>{
  console.log('obj changed ',newValue,oldValue);
})
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
