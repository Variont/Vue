<template>
  <div class="app">
      <form @submit.prevent>
        <h4>Добавление нового поста</h4>
        <input
            v-bind:value="title"
            @input="title = $event.target.value"
            class="input"
            type="text"
            placeholder="Название"
        >
        <input
            v-bind:value="body"
            @input="body = $event.target.value"
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

    <div class="post" v-for="post in posts">
      <div><strong>Название: </strong>{{post.title}}</div>
      <div><strong>Описание: </strong>{{post.body}}</div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      posts: [
        {id: 1, title: "Пост о JavaScript ", body: "JavaScript Говно! TypesScript Охонь."},
        {id: 2, title: "Пост о JavaScript 2", body: "JavaScript Говно 2! TypesScript Охонь 2."},
        {id: 3, title: "Пост о JavaScript 3", body: "JavaScript Говно 3! TypesScript Охонь 3."},
        {id: 4, title: "Пост о JavaScript 4", body: "JavaScript Говно 4! TypesScript Охонь 4."}
      ],
      title: '',
      body: '',
    }
  },

  methods: {
    createPost() {
      const newPost = {
        id: Date.now(),
        title: this.title,
        body: this.body
      }
      this.posts.push(newPost)
      this.title = ''
      this.body  = ''
    },
    inputTitle(event) {
      this.title = event.target.value;
    }
  }
}
</script>

<style>

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

form{
  display: flex;
  flex-direction: column;
}

.app{
  padding: 50px;
}

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

.post {
  padding: 15px;
  margin-top: 1%;
  border: 3px solid cornflowerblue;
  border-radius: 15px;
}


</style>