<template>
  <section class="bg-gray-100">
    <Container>
      <div class="h-screen flex items-center justify-center">
        <div class="w-[500px]">
          <img
            class="w-[full] h-[500px] object-cover"
            src="/images/bg-error.png"
            alt="error"
          />
        </div>

        <div class="p-10">
          <h1
            class="text-[60px] leading-[74px] font-medium text-[#47B886] mb-3"
          >
            404 not found
          </h1>
          <h2 class="text-[28px] leading-[34px] text-[#89CCAA] mb-3">
            Looking something we don’t serve?
          </h2>

          <nuxt-link
            to="/"
            class="text-[23px] leading-[28px] text-[#295040] hover:underline"
            >back to home</nuxt-link
          >
        </div>
      </div>
    </Container>
  </section>
</template>

<script setup></script>

<style lang="scss" scoped></style>
