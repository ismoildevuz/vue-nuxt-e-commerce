<template>
  <div class="border-t-2 border-gray-300 mx-3 select-none">
    <div
      @click="el.isOpen = !el.isOpen"
      class="flex items-center justify-between py-3 cursor-pointer"
    >
      <h6 class="h6">
        <span>{{ el.name }}</span>
      </h6>

      <Icons
        :name="el.isOpen ? 'expand_less' : 'expand_more'"
        color="#8B96A5"
      />
    </div>

    <div v-if="el.isOpen" class="mb-5 body">
      <div
        v-for="(item, index) in el.items"
        :key="index"
        class="flex items-center gap-2 py-[6px]"
      >
        <input
          v-show="el.type == 'checkbox'"
          type="checkbox"
          v-model="item.checked"
        />
        <h6>
          <span>{{ item.name }}</span>
        </h6>
      </div>

      <div class="flex items-center justify-between py-[6px]">
        <h6><span class="text-primary">See all</span></h6>
      </div>
    </div>
  </div>
</template>

<script setup>
const props = defineProps(["el"]);
</script>

<style lang="scss" scoped></style>
