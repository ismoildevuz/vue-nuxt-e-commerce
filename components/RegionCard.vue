<template>
  <div class="flex items-center gap-3">
    <img
      class="w-[35px] h-[25px] object-cover"
      :src="`/images/${el.image}`"
      alt="reg"
    />

    <div>
      <h6 class="h6">
        <span class="font-medium">{{ el.name }}</span>
      </h6>

      <h6 class="body-sm-muted">
        <span>{{ el.site }}</span>
      </h6>
    </div>
  </div>
</template>

<script setup>
const props = defineProps(["el"]);
</script>

<style lang="scss" scoped></style>
