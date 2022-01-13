<template>
  <div class="app">
    <form>
      <h4>Создание поста:</h4>
      <input
          v-bind:value="title"
          @input="inputTitle"
          class="input"
          type="text"
          placeholder="Название"
      >
      <input
          v-bind:value="body"
          @input="body = $event.target.value"
          class="input"
          type="text"
          placeholder="Описание"
      >
      <button class="btn" @click="createPost">Создать</button>
    </form>
    <div class="post" v-for="post in posts">
      <div><strong>Название:</strong> {{ post.title }}</div>
      <div><strong>Описание:</strong> {{ post.body }}</div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      posts: [
        {id: 1, title: 'JavaScript 1', body: 'Описание поста 1'},
        {id: 2, title: 'JavaScript 2', body: 'Описание поста 2'},
        {id: 3, title: 'JavaScript 3', body: 'Описание поста 3'},
      ],
      title: '',
      body: '',
    }
  },
  methods: {
    createPost() {

    },
    inputTitle(event) {
      this.title = event.target.value;
    },
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

.input {
  width: 100%;
  border: 1px solid teal;
  padding: 10px 15px;
  margin-top: 15px;
}

.app {
  padding: 20px;
}

form {
  display: flex;
  flex-direction: column;
}

.btn {
  margin-top: 15px;
  padding: 10px 15px;
  align-self: flex-end;
  background: none;
  color: teal;
  border: 1px solid teal;
}
</style>
