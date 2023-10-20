<template>
  <div class="post">
    <div>
      <div><strong>Название: </strong>{{ post.title }}</div>
      <div><strong>Описание: </strong>{{ post.body }}</div>
    </div>
    <div>
      <my-button
          class="btn_item"
          @click="$emit('removePost', post)"
      >
        {{ this.btmName }}
      </my-button>
    </div>
  </div>
</template>

<script>

import MyButton from "@/components/UI/MyButton";
export default {
  name: "PostItem",
  components: {MyButton},
  data() {
    return {
      btmName: 'Удалить'
    }
  },
  props: {
    post: {
      type: Object,
      required: true
    },
  },
}
</script>

<style scoped>
.post {
  padding: 15px;
  margin-top: 1%;
  margin-bottom: 1%;
  border: 3px solid cornflowerblue;
  border-radius: 15px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

</style>