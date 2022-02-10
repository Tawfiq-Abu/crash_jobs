<template>
  <div class="home">
    home 
    <p ref="p">My name is {{name}} and i'm {{age}} years of age</p>
    <button @click="handleClick">click me</button>
    <button @click="age++">add 1 to age</button>
    <input type="text" v-model="name">
  </div>
</template>

<script>
import { ref } from '@vue/reactivity'
// @ is an alias to /src


export default {
  name: 'Home',
  setup(){
    const p = ref(null)
    
    
    const name =ref('Tawfiq')
    const age = ref(21)


    const handleClick = () =>{
      console.log(p,p.value)
      name.value= 'crash'
    }

    return { name,age,handleClick,p}
  }
 
}
</script>
