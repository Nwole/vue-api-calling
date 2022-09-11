<template>
  <div class="form-container">
    <v-container @submit.prevent="createPost" class="form">
      <div>
        <label>Post user id</label>
        <v-text-field outlined type="text" id="userId" v-model="formData.userId" />
      </div>
      <div>
        <label>Post title</label>
        <v-text-field outlined type="text" id="title" v-model="formData.title" />
      </div>  <div>
        <label>Post body</label>
        <v-text-field outlined type="text" id="body" v-model="formData.body" />
      </div>
      <v-btn @click="createPost" depressed color="orange">Create Post</v-btn>
    </v-container>
  </div>
</template>

<script>
  import axios from 'axios'
export default {
  name: 'CreatePost',
  data(){
    return{
      formData:{
        userId: '',
        title: '',
        body: ''
      }
    }
  },
  methods:{
    createPost(){
      axios.post("https://jsonplaceholder.typicode.com/posts", this.formData)
      .then(response => console.log(response))
      .then(error => console.log(error))
    }
  }
};
</script>

<style>
  /* .form-container{
    width: 100%;
    background: aquamarine;
  } */
  /* .form{
    width: 50%
  } */
</style>
