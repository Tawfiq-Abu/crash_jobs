<template>
  <div class="post">
      <p>{{post.title}}</p>
      {{snippet}}
  </div>
</template>

<script>
import { computed } from '@vue/runtime-core'
export default {
    props:['post'],
    setup (props){
        const snippet = computed(()=>{
            return props.post.body.substring(0,60) + '.....'
        })
        return{ snippet}
    }
}
</script>

<style>

</style>