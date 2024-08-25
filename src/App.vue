<template>
  <Person a="test" :list="personList"/>
</template>
<script setup name="App" lang="ts">
  import Person  from '@/Component/Person.vue';
  import {reactive} from 'vue'
  import {type Persons} from '@/typys'
  let personList = reactive<Persons>([
   {id:'1',name:'luck',age:20},
   {id:'2',name:'luck2',age:21},
   {id:'3',name:'luck3',age:22}
  ]);
</script>
<style>
/* style */
.app{
    background-color: aliceblue;
    box-shadow: 0 0 10px;
    border-radius: 20px;
    padding: 20px;
}
</style>
