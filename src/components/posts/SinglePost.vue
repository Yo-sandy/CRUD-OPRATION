<template>
<ul class="list-group">
    <li class="list-group-item text-start" v-for="post in posts" :key="post.id">
      <p>
        <strong>Post ID: {{ post.id }} </strong>
      </p>
      <p>
        <strong>Title :</strong>
        {{ post.title}}
      </p>
      <p>
        <strong>Body :</strong>
        {{ post.body }}
      </p>
      <p>
        <strong>User ID:</strong>
        {{ post.userId }}
      </p>
    </li>
</ul>
</template>

<script>
export default {
   props:{
     posts:{
       type:Array,
       required:true,
     },
   },
};
</script>
