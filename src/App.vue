<template>
  <v-app>
    <v-container>
      <CreatePost/>
      <PostList />
    </v-container>
    <v-main>
      <router-view />
    </v-main>
  </v-app>
</template>

<script>
import PostList from "./components/PostList.vue";
import CreatePost from "./components/CreatePost.vue";

export default {
  name: "App",
  data: () => ({
    //
  }),
  components: { PostList, CreatePost },
};
</script>
<style scoped>
/* .components-container{
  width: 70%;
  background: aquamarine;
} */
</style>
