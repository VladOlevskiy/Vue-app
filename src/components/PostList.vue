<template lang="">
  <div v-if="list.length > 0">
    <h3>Список користувачів</h3>
    <PostItem
      @remove="$emit('remove', item)"
      :key="item.id"
      :item="item"
      v-for="item in list"
    />
  </div>
  <h2 v-else style="color: red">Список постів пустий</h2>
</template>

<script>
import PostItem from "./PostItem.vue";
export default {
  components: { PostItem },
  props: {
    list: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style scoped></style>
