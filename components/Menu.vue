<template>
  <div class="h6 border-y-2 border-gray-300 hidden 2xl:block">
    <Container>
      <div class="py-5 flex items-center justify-between">
        <div class="flex items-center gap-10">
          <div class="flex items-center gap-3">
            <Icons name="menu" />

            <span>All category</span>
          </div>

          <span>Hot offers</span>

          <span>Gift boxes</span>

          <span>Projects</span>

          <span>Menu item</span>

          <div class="flex items-center cursor-pointer select-none">
            <span>Help</span>

            <Icons name="expand_more" color="#8B96A5" />
          </div>
        </div>

        <div class="flex items-center gap-10">
          <div class="flex items-center cursor-pointer select-none">
            <span>English, USD</span>

            <Icons name="expand_more" color="#8B96A5" />
          </div>

          <div class="flex items-center gap-2 cursor-pointer select-none">
            <span>Ship to</span>

            <img
              class="w-[21px] h-[15px] object-cover"
              src="/images/de.png"
              alt=""
            />

            <Icons name="expand_more" color="#8B96A5" />
          </div>
        </div>
      </div>
    </Container>
  </div>
</template>

<script setup></script>

<style lang="scss" scoped></style>
