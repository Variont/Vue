<template>
  <form @submit.prevent>
    <h4>Добавление нового поста</h4>
    <input
        :value="post.title"
        @input="post.title = $event.target.value"
        class="input"
        type="text"
        placeholder="Название"
    >
    <input
        :value="post.body"
        @input="post.body = $event.target.value"
        class="input"
        type="text"
        placeholder="Описание поста"
    >
    <button
        class="btn"
        @click="createPost"
    >
      Создать
    </button>
  </form>
</template>

<script>
export default {
  name: "PostForm",
  data() {
    return {
      post: {
       title: '',
       body: '',
      }
    }
  },
  methods: {
    createPost() {
      this.post.id = Date.now()
      this.$emit('createPost', this.post)
      this.post = {
        title: '',
        body: '',
      }
    }
  }
}

</script>

<style scoped>
.input {
  width: 100%;
  border: 2px solid cornflowerblue;
  padding: 15px 15px;
  margin-top: 1%;
  border-radius: 20px;
}

.btn{
  align-self: flex-end;
  margin-top: 1%;
  padding: 10px 15px;
  border:3px solid cornflowerblue;
  background: none;
  color: cornflowerblue;
  border-radius: 15px;

}
</style>