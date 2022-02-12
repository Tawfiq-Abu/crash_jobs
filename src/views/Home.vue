<template>
  <div class="home">
   <h1>Home</h1>
   <h2>Refs</h2>
   <p>{{ crashOne.name }} - {{crashOne.age}}</p>
   <button @click="updateCrashOne">update CrashOne</button>

   <h2>Reactive</h2>
   <p>{{ crashTwo.name}}-{{crashTwo.age}}</p>
   <button @click="updateCrashTwo">update CrashTwo</button>

  </div>
</template>

<script>
import { ref,reactive } from '@vue/reactivity'
// @ is an alias to /src


export default {
  name: 'Home',
  setup(){
    const crashOne = ref({name:'tawfiq',age:21})
    const crashTwo = reactive({name:'Machele',age:25})

    const updateCrashOne = () =>{
      crashOne.value.age = 22
    }

    const updateCrashTwo = () =>{
      crashTwo.age = 28
    }

    return { crashOne,updateCrashOne,crashTwo,updateCrashTwo}
  }
 
}
</script>
