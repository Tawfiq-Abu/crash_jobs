<template>
  <div class="home">
   <h1>Home</h1>
   <input type="text" v-model="search">
   <div v-for="name in namesMatching" :key="name">{{name}}</div>
   <p>search term -{{search}}</p>
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
import { computed } from '@vue/runtime-core'
// @ is an alias to /src


export default {
  name: 'Home',
  setup(){
    const crashOne = ref({name:'tawfiq',age:21})
    const crashTwo = reactive({name:'Machele',age:25})
    const search = ref('')

    const names = ref(['tawfiq','machele','aania','kudra','saachibu','queenie bash','salamatu'])
    // const name = computed(()=>{
    //   // the computed function returns a value which would be what the constant is equal to
    //   // computed property computes a new value based of of other values
    //   // we used it in the past to return filtered versions of data
    //   return 'tawfiq'
    // })
    const namesMatching = computed(()=>{
      return names.value.filter((name)=> name.includes(search.value))
    })

    const updateCrashOne = () =>{
      crashOne.value.age = 22
    }

    const updateCrashTwo = () =>{
      crashTwo.age = 28
    }

    return { crashOne,updateCrashOne,crashTwo,updateCrashTwo,names,search,namesMatching}
  }
 
}
</script>
