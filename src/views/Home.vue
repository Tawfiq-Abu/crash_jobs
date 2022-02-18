<template>
  <div class="home">
   <h1>Home</h1>
   <PostList v-if="showPost" :posts="posts"/>
   <button @click="showPost = !showPost">show posts</button>
   <button @click="posts.pop()">delete post</button>
  </div>
</template>

<script>
import SinglePost from '../components/SinglePost.vue'
import { ref,reactive } from '@vue/reactivity'
import PostList from '../components/PostList.vue'
// @ is an alias to /src


export default {
  components: { PostList,SinglePost },
  name: 'Home',
  setup(){
    const posts = ref([
      { title:'Welcome to the blog',body:'Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quis quia incidunt similique minus dolor explicabo facilis maxime doloremque quidem vitae.',id:1},
      { title:'Top 5 css tips',body:'Lorem ipsum',id:2}

    ])
    const showPost = ref(true)

    return { posts,showPost}
  }
 
}
</script>
