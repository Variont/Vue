<template>
  <div class="post" v-for="post in posts">
    <div><strong>Название: </strong>{{post.title}}</div>
    <div><strong>Описание: </strong>{{post.body}}</div>
  </div>
</template>

<script>
export default {
  name: "PostList",
  props:{
    posts:{
      type: Array,
      required: true
    }
  }
}
</script>

<style scoped>

.post {
  padding: 15px;
  margin-top: 1%;
  border: 3px solid cornflowerblue;
  border-radius: 15px;
}

</style>