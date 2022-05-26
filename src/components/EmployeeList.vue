<template>
  <div>
    <h1>Employee List</h1>
    <button v-on:click="getdata()">LOAD POST</button>
  </div>
</template>


<script>
import axios from 'axios'



export default{
  name:"EmployeesList",
  data(){
    return{
      post:[],

    }
  } ,
methods:{
getdata(){
     axios.get('https://jsonplaceholder.typicode.com/posts')
     .then(response=>{
       console.log(response.data);
       this.post=response;
     }).catch(error=>console.log(error));
  }
}
  
};
</script>