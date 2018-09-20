<template>
  <div class="posts">
    <h1>Posts</h1>
    This file will list all the posts.

    <div v-for="post in posts" :key="post">
      <p>
        <span><b>{{ post.color }}</b></span><br />
        <span>{{ post.value }}</span>
      </p>
    </div>
  </div>
</template>

<script>
//import PostsService from 'services/PostsService'
import modelrotater from '../ThreeDRenderer/threeDimplementation'
import axios from 'axios'
export default {
  name: 'posts',
  data () {
    return {
        
        posts: []
        
    }
  },
  mounted () {
    debugger;
    this.getPosts()
  },
  methods: {
    getPosts () {
        debugger;
        axios.get('http://localhost:8081/').then(response=>{
            debugger;
            this.posts = response.data;
        })
    }
  }
}
</script>