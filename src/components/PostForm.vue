<template>
    <div class="app">
      <form @submit.prevent>
          <h4>Создание поста</h4>
          <my-input v-model="post.title" type="text" placeholder="Название"/>
          <my-input v-model="post.body" type="text" placeholder="Описание"/>
          <my-button @click="createPost">Создать</my-button>
      </form>
    </div>
</template>

<script>
    export default {
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

</style>