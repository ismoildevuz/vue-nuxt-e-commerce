<template>
  <div
    class="p-5 bg-white border-2 border-gray-300 rounded-lg overflow-hidden"
  >
    <img
      class="w-[150px] h-[150px] 2xl:w-[200px] 2xl:h-[200px] object-cover mb-3 2xl:mb-5"
      :src="`/images/${el.image}`"
      alt="rec"
    />

    <h6 class="h6 mb-1 2xl:mb-3">
      <span>${{ el.price }}</span>
    </h6>

    <h6 class="body-muted">
      <span>{{ el.description }}</span>
    </h6>
  </div>
</template>

<script setup>
const props = defineProps(["el"]);
</script>

<style lang="scss" scoped></style>
