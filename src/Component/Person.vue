<template>
  <div class="person">
    ???
  </div>
</template>
<script setup name="Person" lang="ts">
import { type PersonInter,type Persons} from '@/typys';
//let person:PersonInter = {id:'1',name:'Luck',age:11};
let personList:Persons=[
  {id:"1",name:"luck1",age:60},
  {id:"2",name:"luck2",age:60},
  {id:"3",name:"luck3",age:60},
]
</script>
<style>
.person{
    background-color: aliceblue;
    box-shadow: 0 0 10px;
    border-radius: 20px;
    padding: 20px;
}
</style>