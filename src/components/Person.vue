<template>
  <div class="person">
   <h2>name:{{ person.name }}</h2>
   <h2>name:{{ person.age }}</h2>
   <button @click="changeName" class="button">change name</button>
   <button @click="changeAge"> changeAge</button>
  </div>  
</template>
<!-- install vue plugin fsr set up :this is not define vue component name -->
 <!--npm i vite-plugin-vue-setup-extend -D  -->
 <!--then config the vite.config.ts  -->
<script setup name="Person223">
// structure data still is reactive data by wrapper toRefs
import { reactive,toRefs } from 'vue';
let person = reactive({
  name: 'John Doe',
  age: 30
});
let {name,age} = toRefs(person)
function changeName() {
  name.value += '~'
}
function changeAge() {
  age.value += 1
}
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
