<template>
  <div
    class="bg-white border-2 border-gray-300 rounded-lg overflow-hidden mx-5 2xl:mx-0 flex items-center gap-5 2xl:block p-2"
  >
    <div
      class="flex justify-center items-center h-full 2xl:h-auto 2xl:border-b-2 2xl:border-gray-300 flex-shrink-0"
    >
      <img
        class="w-[80px] 2xl:w-[230px] h-[100px] 2xl:h-[230px] object-cover 2xl:mb-5"
        :src="`/images/${el.image}`"
        alt="mobile"
      />
    </div>

    <div class="2xl:p-5">
      <div class="flex justify-between">
        <div>
          <div class="flex items-baseline gap-3 mb-1">
            <h5 class="h5">
              <span>{{ el.newPrice }}</span>
            </h5>
            <h6 class="h6">
              <span class="text-gray-500 font-normal line-through">{{
                el.oldPrice
              }}</span>
            </h6>
          </div>

          <div class="flex items-center gap-2">
            <div class="flex items-center">
              <div
                v-for="(el, ind) in Math.floor(el.rating)"
                :key="ind"
                class="flex items-center"
              >
                <Icons name="star" color="#FF9017" size="20" />
              </div>

              <div
                v-if="el.rating != Math.floor(el.rating)"
                class="flex items-center"
              >
                <Icons name="star_half" color="#FF9017" size="20" />
              </div>

              <div
                v-if="
                  1 <= 5 - Math.ceil(el.rating) &&
                  el.rating == Math.floor(el.rating)
                "
                v-for="(el, ind) in 5 - Math.floor(el.rating)"
                :key="ind"
                class="flex items-center"
              >
                <Icons name="star_border" color="#FF9017" size="20" />
              </div>

              <div
                v-if="
                  1 <= 5 - Math.ceil(el.rating) &&
                  el.rating != Math.floor(el.rating)
                "
                v-for="(el, ind) in 4 - Math.floor(el.rating)"
                :key="ind"
                class="flex items-center"
              >
                <Icons name="star_border" color="#FF9017" size="20" />
              </div>
            </div>

            <h6 class="body-sm 2xl:body pt-1 2xl:pt-0">
              <span class="text-orange">{{ el.rating }}</span>
            </h6>

            <div class="flex items-center gap-1 2xl:hidden pt-1 2xl:pt-0">
              <div class="bg-gray-500 w-1 h-1 rounded-full"></div>

              <h6 class="body-sm-muted">
                <span>{{ el.orders }} orders</span>
              </h6>
            </div>
          </div>
        </div>

        <div
          class="hidden w-[37px] h-[37px] 2xl:flex items-center justify-center border-2 border-gray-300 rounded-lg"
        >
          <Icons name="favorite_border" color="#0D6EFD" />
        </div>
      </div>

      <h6 class="h6 2xl:body 2xl:w-[240px] pt-2">
        <span class="text-gray-600 font-normal">{{ el.description }}</span>
      </h6>

      <h6 class="2xl:hidden body w-[240px] pt-2">
        <span class="text-green">Free shipping</span>
      </h6>
    </div>
  </div>
</template>

<script setup>
const props = defineProps(["el"]);
</script>

<style lang="scss" scoped></style>
