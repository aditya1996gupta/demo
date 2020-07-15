<template>
<div>
  <ul v-if="posts && posts.length">
    <div v-for="(post,index) of posts" :key='index'>
      <p><strong>{{post.id}}</strong> . <strong>{{post.title}}</strong></p>
      <p>{{post.body}}</p>
    </div>
  </ul>

  <ul v-if="errors && errors.length">
    <li v-for="error of errors" :key='error'>
      {{error.message}}
    </li>
  </ul>
</div>
</template>

<script>
import axios from 'axios'

export default {
  data () {
    return {
      posts: [],
      errors: []
    }
  },
  async created () {
    try {
      const response = await axios.get(`http://jsonplaceholder.typicode.com/posts`)
      this.posts = response.data
    } catch (e) {
      this.errors.push(e)
    }
  }
}
</script>
