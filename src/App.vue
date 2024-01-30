<template>
  <div class="app">
    <div>
      <form>
        <h4>Создание поста</h4>
        <input class="input" type="text" placeholder="Название">
        <input class="input" type="text" placeholder="Описание">
        <button class="btn" @click="createPost">Создать</button>
      </form>
    </div>
    <div class="post" v-for="post in posts" v-bind:key="post">
      <div><strong>Название:</strong>{{ post.title }}</div>
      <div><strong>Описание:</strong>{{ post.body }}</div>
    </div>
  </div>

</template>

<script>

export default {
  data() {
    return {
      posts: [
        {id: 1, title:'JavaScript', body:'Описание поста'},
        {id: 2, title:'JavaScript 2', body:'Описание поста 2'},
        {id: 3, title:'JavaScript 3', body:'Описание поста 3'},
        {id: 4, title:'JavaScript 4', body:'Описание поста 4'},
      ]
    }
  },
  methods: {
    addLike() {
      this.likes +=1;
    },
    addDislike() {
      this.dislikes +=1;
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
.post {
  padding: 15px;
  border: 2px solid teal;
  margin-top: 15px;
}
form {
  display: flex;
  flex-direction: column;
}
.app {
  padding: 20px;
}
.input {
  width: 100%;
  border: 1px solid teal;
  padding: 10px 15px;
  margin-top: 15px;
}
.btn {
  margin-top: 15px;
  align-self: flex-end;
  padding: 10px;
  background: none;
  color: teal;
  border: 1px solid teal;
}
</style>