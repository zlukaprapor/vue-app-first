<template>
  <div>
    <form @submit.prevent>
      <h4>Создание поста</h4>
      <input
        v-model="post.title"
        class="input"
        type="text"
        placeholder="НАЗВАНИЕ"
      />
      <input
        v-model="post.body"
        class="input"
        type="text"
        placeholder="ОПИСАНИЕ"
      />
      <button class="btn" @click="createPost">Добавить</button>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      post: {
        title: '',
        body: '',
      },
    };
  },
  methods: {
    createPost() {
      this.post.id = Date.now();
      this.$emit('create', this.post);
      this.post = {
        title: '',
        body: '',
      };
    },
  },
};
</script>

<style scoped>
form {
  display: flex;
  flex-direction: column;
}
.input {
  width: 100%;
  border: 2px solid green;
  padding: 10px 10px;
  margin: 10px;
}
.btn {
  margin-top: 20px;
  align-self: flex-end;
  padding: 10px;
  background: none;
  color: red;
  border: 2px solid green;
}
</style>
