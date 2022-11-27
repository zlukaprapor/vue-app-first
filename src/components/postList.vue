<template>
  <div>
    <div class="post" v-for="post in posts">
      <div><strong>НАЗВАНИЕ</strong>{{ post.title }}</div>
      <div><strong>ОПИСАНИЕ</strong>{{ post.body }}</div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    type: Array,
    required: true,
  },
};
</script>

<style scoped>
.post {
  margin-top: 15px;
  padding: 20px;
  border: 2px solid green;
}
</style>
