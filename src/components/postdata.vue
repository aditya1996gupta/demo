<template>
<div>
  <h1 id='head'> Pushing Data with a POST Request </h1>
  <input type="text" placeholder='check n/w section in developer area for post result' v-model="postBody" v-on:change="test ()"/>
  <ul v-if="errors && errors.length">
    <li v-for="error of errors" :key='error'>
      {{error.message}}
    </li>
  </ul>
</div>
</template>

<script>
import { HTTP } from '@/httpcommon.js'
import axios from 'axios'
export default {
  data () {
    return {
      postBody: '',
      errors: []
    }
  },
  methods: {
    test: function () {
      axios.post(`http://jsonplaceholder.typicode.com/posts`, {
        body: this.postBody
      })
        .then(response => {})
        .catch(e => {
          this.errors.push(e)
        })
    }
  },
  created () {
    HTTP.get(`posts`)
      .then(response => {
        this.posts = response.data
      })
      .catch(e => {
        this.errors.push(e)
      })
  }
}
</script>

<style>
#head{
 margin: auto;
 width: 50%;
 padding: 2px;
 justify-content: center;
 left: 0;
 top: 0;
 width: 50vw;
}
input{
  margin: auto;
  width: 10%;
  border: 1px solid green;
  padding: 2px;
  display: flex;
  justify-content: center;
  left: 0;
  top: 0;
  width: 25vw;
}
</style>
