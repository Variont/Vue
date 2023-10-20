<template>
  <form @submit.prevent>
    <h4>Добавление нового поста</h4>
    <my-input
        v-model="post.title"
        type="text"
        placeholder="Название"
    />
    <my-input
        v-model="post.body"
        type="text"
        placeholder="Описание поста"
    />
    <my-button
        class="btn_form"
        @click="createPost"
        :btn-name='this.btnName'
    >
      {{this.btnName}}
    </my-button>
  </form>
</template>

<script>
import MyInput from "@/components/UI/MyInput";
import MyButton from "@/components/UI/MyButton";
export default {
  name: "PostForm",
  components: {MyButton, MyInput},
  data() {
    return {
      post: {
       title: '',
       body: '',
      },
      btnName:'Создать',
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
.btn_form {
  margin-top: 1%;
}
</style>