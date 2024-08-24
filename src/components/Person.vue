<template>
  <div class="person">
    <h1>Person Page</h1>
    <div>Name: {{ name }}</div>
    <div>Age: {{ age }}</div>
    <button @click="changeName" class="button">change name</button>
    <button @click="changeAge" class="button">change name</button>
    <hr>
    <div>{{ a }}</div>
    <div>{{ b }}</div>
  </div>
</template>

<script>
export default {
  name: 'Person',
  data(){
    return {
      a:this.name,  
      b:this.age
    }
  },
  setup(){
    //data Note：Your Vue.js component is almost correct
    let name = 'John Doe';
    let age = 30;
    function changeName(){
        name = 'Luck';
    }
    function changeAge(){
        age +=1;
    }
    return {name,age,changeAge,changeName};
  }
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
