<template>
  <div class="person">
    <h1>Person Page</h1>
    <div>Name: {{ name }}</div>
    <div>Age: {{ age }}</div>
    <button @click="changeName" class="button">change name</button>
    <button @click="changeAge" class="button">change name</button>
  </div>
</template>
<!-- install vue plugin for set up :this is not define vue component name -->
 <!--npm i vite-plugin-vue-setup-extend -D  -->
 <!--then config the vite.config.ts  -->
<script setup name="Person223">
// define the basic type data 
import{ref} from 'vue'
  //data is not reactive recently
  // use ref wrapper data that make the data reactive
  let name = ref('John Doe');
  let age = ref(30);
  console.log(name)
  console.log(age)

  function changeName(){
      name = 'Luck';
  }
  function changeAge(){
      age +=1;
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
