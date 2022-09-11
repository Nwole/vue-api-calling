<template>
  <v-container>
    <!-- <v-btn @click="getPosts" depressed  color="red" dark class="bg-orange-400">Load Post List</v-btn> -->
    <h3 class="text-red-400" v-if="errorMessage">{{errorMessage}}</h3>
    <div class="bg-green-200 p-4 m-4 rounded-lg text-red-400 shadow-xl w-50" v-for="post in posts" :key="post.id">
        <h3 class="m-4">{{post.id}} {{post.title}}</h3>
        <p>{{post.body}}</p>
        <hr/>
    </div>
  </v-container>
</template>

<script>
import axios from "axios";
export default {
  name: "PostList",
  created(){
    this.getPosts()
  },
  data() {
    return {
      posts: [],
      errorMessage: ''
    };
  },
  methods: {
    getPosts() {
      axios
        .get("https://jsonplaceholder.typicode.com/posts?_limit=10")
        .then((respond) => {
          console.log(respond.data);
          this.posts = respond.data
        })
        .catch((error) => {
          console.log(error);
          this.errorMessage = 'Error retrieving data'
        });
    },
  },
};
</script>

<style></style>
