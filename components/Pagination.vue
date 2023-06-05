<template>
  <div class="flex justify-center 2xl:justify-end my-10">
    <div class="flex items-center gap-2">
      <div class="relative">
        <Icons
          class="absolute top-[25%] right-2"
          name="expand_more"
          color="#8B96A5"
        />
        <select
          name="pcs"
          id="pcs"
          class="font-normal border-2 border-gray-300 rounded-lg w-[110px] p-2 appearance-none"
        >
          <option value="10" selected>Show 10</option>
          <option value="20">Show 20</option>
          <option value="30">Show 30</option>
          <option value="40">Show 40</option>
        </select>
      </div>

      <div class="h6 flex bg-white border-2 border-gray-300 rounded-lg">
        <div class="flex items-center justify-center p-2 border-r-2">
          <Icons name="chevron_left" />
        </div>

        <div class="flex items-center justify-center w-[40px] border-r-2">
          <h6><span>1</span></h6>
        </div>

        <div class="flex items-center justify-center w-[40px] border-r-2">
          <h6><span>2</span></h6>
        </div>

        <div class="flex items-center justify-center w-[40px] border-r-2">
          <h6><span>3</span></h6>
        </div>

        <div class="flex items-center justify-center p-2">
          <Icons name="chevron_right" />
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
const props = defineProps(["el"]);
</script>

<style lang="scss" scoped></style>
