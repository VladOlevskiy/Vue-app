<template>
  <form class="form" @submit.prevent>
    <h3>Створення поста</h3>
    <my-input v-model="post.title" type="text" placeholder="Назва" />
    <my-input v-model="post.body" type="text" placeholder="Опис" />
    <my-button class="btn__create" @click="createPost">Створити</my-button>
  </form>
</template>
<script>
export default {
  data() {
    return {
      post: {
        title: "",
        body: "",
      },
    };
  },
  methods: {
    createPost() {
      this.post.id = Date.now();

      this.$emit("create", this.post);
      this.post = {
        title: "",
        body: "",
      };
    },
  },
};
</script>
<style>
.form {
  display: flex;
  flex-direction: column;
}
.btn__create {
  margin-top: 15px;
  align-items: flex-end;
}
</style>
