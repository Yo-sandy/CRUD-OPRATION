<template>
<div class="container">
  <div class="row">
    <div class="col-md-12">
      <h2 class="text-center bg-primary p-3 text-white fw-bold">Posts</h2>
      <Create-post/>
      <single-post :posts="posts"/>
    </div>
  </div>
</div>
</template>

<script>

import SinglePost from "./posts/SinglePost.vue";
import CreatePost from "./posts/CreatePost.vue";
export default {
  name: "Posts",
  components: {
    SinglePost,
    CreatePost
  },
  data(){
    return{
      posts:[],
    };
  },
  mounted() {
    this.getPosts();
  },
  methods:{
    async getPosts(){
      const { data } = await  this.axios.get(
          "https://jsonplaceholder.typicode.com/posts"
      );
      this.posts = data;
    },
  },
};
</script>

<style scoped>

</style>