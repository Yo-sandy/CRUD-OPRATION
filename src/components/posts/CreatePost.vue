<template>
<div class="mb-2">
  <label for="title">Title</label>
  <input
      id="title"
      type="text"
      placeholder="Enter your title"
      class="form-control"
      v-model="post.title"
  />
</div>
  <div class="mb-2">
    <label for="title">Body</label>
    <textarea class="form-control" v-model="post.body"></textarea>
  </div>
  <div class="mb-2">
    <label for="title">User ID</label>
    <input type="text" v-model="post.userId" class="form-control"/>
  </div>
  <button class="btn btn-outline-primary mb-3" @click="savePost">Save Post</button>
</template>

<script>
export default {
  data(){
    return{
      post:{
        title: "",
        userId: 10,
        body: "",
      },
    };
  },
  methods:{
    async savePost(){
      const  response = await  this.axios.post(
          "https://jsonplaceholder.typicode.com/posts",
          {
            title: this.post.title,
            body: this.post.body,
            userId: this.post.userId,
          }
      );
      if (response.status === 201){
        console.log("post created");
      }
    },
  },
};
</script>
