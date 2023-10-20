<template>
  <div class="app">
    <post-form
        @createPost="createPost"/>
    <post-list
        :posts="posts"
        @removePost="removePost"
    />
  </div>
</template>

<script>
import PostForm from "@/components/PostForm"
import PostList from "@/components/PostList"

export default {
  components: {
    PostList, PostForm
  },
  data() {
    return {
      posts: [
        {id: 1, title: "Пост о JavaScript ", body: "JavaScript Говно! TypesScript Охонь."},
        {id: 2, title: "Пост о JavaScript 2", body: "JavaScript Говно 2! TypesScript Охонь 2."},
        {id: 3, title: "Пост о JavaScript 3", body: "JavaScript Говно 3! TypesScript Охонь 3."},
        {id: 4, title: "Пост о JavaScript 4", body: "JavaScript Говно 4! TypesScript Охонь 4."}
      ],
    }
  },

  methods: {
    createPost(newPost) {
      if (newPost.title === '' || newPost.body === '') {
        return
      }
      this.posts.push(newPost)
    },
    removePost(post) {
      this.posts = this.posts.filter(oldPost => oldPost.id !== post.id)
    },
  },
}
</script>

<style>

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

form {
  display: flex;
  flex-direction: column;
}

.app {
  padding: 50px;
}


</style>