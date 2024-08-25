<template>
  <div class="person">
    <div>{{ a }}</div>
    <ul>
      <li v-for="person in list" :key="person.id">{{ person.name }} ~{{ person.age }}~{{ person.id }}</li>
    </ul>
  </div>
</template>
<script setup name="Person" lang="ts">
import {defineProps,withDefaults} from 'vue'
import {type Persons} from '@/typys'
// 只接收list
//let x = defineProps(['a','list'])
//接收 list + 限制类型
//defineProps<{list:Persons}>();
// 接收list + 限制类型+限制必要性 + 指定默认值
// withDefaults(defineProps<{list?:Persons}>(),{
//   list:()=>[{id:'4',name:'luck5',age:50}]
// })
</script>
<style>
.person{
    background-color: aliceblue;
    box-shadow: 0 0 10px;
    border-radius: 20px;
    padding: 20px;
}
</style>