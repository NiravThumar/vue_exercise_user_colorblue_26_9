<template>
  <div>has Lenght : {{ computedLength ?'yes':'No'}}</div>

<div v-if= "computedLength">
  <div>TotalItems : {{computedLength}}</div>
  <table>
    <tr v-for="(value,key) in users" :key="key">
      <td>{{value.id}}</td>
      <td><button class ="btn" :class="{bgGreen:value.status==='active',bgRed:value.status==='inactive'}">{{value.status}}</button></td>
      <td>{{value.firstName +"   " +value.lastName}}</td>
    </tr>
  </table>

</div>


</template>

<script setup>
import {reactive,ref,computed, registerRuntimeCompiler} from 'vue'
let users = reactive([
  {
    id:1,
    status:'active',
    firstName:'ridham',
    lastName :'parmar'
  },
  {
    id:2,
    status:'inactive',
    firstName:'nirav',
    lastName :'thumar'
  }
])

let computedLength =  computed(()=>{
          return users.length
})
</script>

<style scoped>
  .bgGreen{
    background-color: green;
  }
  .bgRed{
    background-color: red;
  }
  .btn{
    width:100px;
    padding:10px 15px;
  }
</style>
