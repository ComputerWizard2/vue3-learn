<template>
  <div class="person">
   <div>{{ sum }}</div>
   <button @click="clickMe">click me</button>

  </div>  
</template>
<!-- install vue plugin fsr set up :this is not define vue component name -->
 <!--npm i vite-plugin-vue-setup-extend -D  -->
 <!--then config the vite.config.ts  -->
<script setup name="Person223">
// structure data still is reactive data by wrapper toRefs
import { watch, ref } from 'vue';
let sum = ref(0);
function clickMe() {
  sum.value +=  1;
}
// watch use to listen to the basical data type
let stopWatch =watch(sum, (newVal, oldVal) => {
  console.log(`sum changed from ${oldVal} to ${newVal}`);
  if(newVal >10){
    stopWatch();
  }
});
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
