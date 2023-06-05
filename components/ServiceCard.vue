<template>
  <div class="bg-white border-2 border-gray-300 rounded-lg overflow-hidden">
    <div class="relative">
      <div class="w-full h-full bg-black top-0 absolute opacity-40"></div>

      <img
        class="w-full h-[150px] object-cover"
        :src="`/images/${el.image}`"
        alt="service"
      />

      <div
        class="absolute -bottom-8 right-5 rounded-full p-5 border-[3px] border-white bg-secondary"
      >
        <Icons :name="el.icon" color="#1C1C1C" />
      </div>
    </div>

    <div class="p-5 w-[240px]">
      <h5 class="h5">
        <span>{{ el.name }}</span>
      </h5>
    </div>
  </div>
</template>

<script setup>
const props = defineProps(["el"]);
</script>

<style lang="scss" scoped></style>
