<template>
  <div v-if="havePosts">
    <h3>Список постов</h3>
    <post-item
        v-for="post in posts"
        :post="post"
        :key="post.id"
        @removePost="$emit('removePost', post)"
    />
  </div>
  <div v-else>
    <h2 style="color: red">
      Посты не найдены
    </h2>
  </div>

</template>

<script>
import PostItem from "@/components/PostItem";
export default {
  name: "PostList",
  components:{ PostItem },
  props:{
    posts:{
      type: Array,
      required: true
    }
  },
  computed: {
    havePosts() {
      return (this.posts.length > 0)
    }
  },

}
</script>

<style scoped>
</style>