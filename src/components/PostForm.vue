<template>
    <div class="app">
      <form @submit.prevent>
          <h4>Создание поста</h4>
          <input v-model="post.title" class="input" type="text" placeholder="Название">
          <input v-model="post.body" class="input" type="text" placeholder="Описание">
          <my-button @click="createPost" class="btn">Создать</my-button>
      </form>
    </div>
</template>

<script>
import MyButton from './UI/MyButton.vue';
    export default {
      components: {
        MyButton
      },
      data() {
        return {
          post: {
            title: '',
            body: ''
          }
        }
      },
      methods: {
        createPost() {
          this.post.id = '';
          this.$emit('create', this.post);
          this.post = {
            title: '',
            body: ''
          }
        }
      }
    }
</script>

<style scoped>
form {
  display: flex;
  flex-direction: column;
}
.input {
  width: 100%;
  border: 1px solid teal;
  padding: 10px 15px;
  margin-top: 15px;
}
</style>