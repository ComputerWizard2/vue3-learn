<template>
  <div class="person">
    <div>brand:{{ car.brand }}</div>
    <div>price:{{ car.price }}</div>
    <hr>
    <div>
      <ul v-for="item in fruit" :key="item.id">
        <li>{{ item.name }}</li>
        <li>{{ item.price }}</li>
      </ul>
    </div>
    <button @click="addPrice" class="button ">add price</button>
    <button @click="addFruit">add fruit</button>
  </div>  
</template>
<!-- install vue plugin for set up :this is not define vue component name -->
 <!--npm i vite-plugin-vue-setup-extend -D  -->
 <!--then config the vite.config.ts  -->
<script setup name="Person223">
// define reference data  
import{ref} from 'vue'
let car =ref({brand:'奔驰',price:100  })
let fruit = ref([
  {id:1,name:'apple',price:10},
  {id:2,name:'banana',price:20}, 
  {id:3,name:'cherry',price:30}
])
function addPrice(){
  // Note: function use reactive object need to .value get real value
  car.value.price += 10
}
function addFruit(){
  // Note: function use reactive object need to .value get real value
  fruit.value.push({
  id: 4,
  name: 'orange',
  price: 40
})
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
