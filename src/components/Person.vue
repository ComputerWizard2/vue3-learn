<template>
  <div class="person">
    <div>name: {{ person.name }}</div>
    <div>age: {{ person.age }}</div>
  </div> 
  <button @click="changeName">change Name</button> 
  <button @click="changePerson">change Person</button> 
</template>
<!-- install vue plugin fsr set up :this is not define vue component name -->
 <!--npm i vite-plugin-vue-setup-extend -D  -->
 <!--then config the vite.config.ts  -->
<script setup name="Person223">
// structure data still is reactive data by wrapper toRefs
import { watch, ref } from 'vue';
let person = ref({
  name:'Jolhe',
  age:12
});
function changeName() {
  person.value.name += "~";
}
function changePerson(){
  console.log(person.value) 
  person.value={name:'Marry', age:22}
}
watch(person, (newValue, oldValue) => {
  console.log(`new value: ${JSON.stringify(newValue)}, old value: ${JSON.stringify(oldValue)}`);
},{deep:true,immediate:true});

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
