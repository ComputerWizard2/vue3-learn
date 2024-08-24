<template>
  <div class="person">
    <h1>Person Page</h1>
    <p>Name: {{ name }}</p>
    <p>Age: {{ age }}</p>
    <button @click="changeName" class="button">change name</button>
    <button @click="changeAge" class="button">change name</button>
  </div>
</template>

<script>
export default {
  name: 'Person',
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
    return ()=>"Hello world";
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
