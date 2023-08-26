<template lang="">
  <div class="post">
    <div>
      <div><strong>Назва</strong> {{ item.title }}</div>
      <div><strong>Опис</strong> {{ item.body }}</div>
    </div>
    <div class="post__btns">
      <my-button @click="$emit('remove', item)">Видалити</my-button>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    item: {
      type: Object,
      required: true,
    },
  },
};
</script>
<style>
.post {
  padding: 15px;
  border: 2px teal solid;
  margin-top: 15px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>
