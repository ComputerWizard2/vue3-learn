<template>
  <div class="person">
   <div>first name: <input v-model="person.firstName"></div>
   
   <div>last name:  <input v-model="person.lastName"></div>
   <div>full name: {{ fullName }}</div>
   <button @click="changeFullName">change full name</button>

  </div>  
</template>
<!-- install vue plugin fsr set up :this is not define vue component name -->
 <!--npm i vite-plugin-vue-setup-extend -D  -->
 <!--then config the vite.config.ts  -->
<script setup name="Person223">
// structure data still is reactive data by wrapper toRefs
import { computed, ref } from 'vue';
let person = ref({
  firstName: 'John ',
  lastName: 'Doe'
});
// computed is read only ,not change. 
let fullName = computed({
  get(){
    return person.value.firstName+"-"+person.value.lastName;
  },
  set(val){
    const [firstName,lastName]= val.split('-');
    person.value.firstName=firstName;
    person.value.lastName=lastName;
  }
})
function changeFullName(){
  fullName.value='luck-hao'
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
