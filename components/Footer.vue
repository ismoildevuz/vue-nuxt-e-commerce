<template>
  <footer class="2xl:block hidden">
    <Container>
      <nav class="py-10 flex gap-40">
        <div class="w-[280px]">
          <img src="/icons/logo.svg" alt="" />

          <p class="body my-5">
            Best information about the company gies here but now lorem ipsum is
          </p>

          <div class="flex gap-2">
            <Icons name="facebook_3" color="#BDC4CD" />
            <Icons name="twitter_3" color="#BDC4CD" />
            <Icons name="linkedin_3" color="#BDC4CD" />
            <Icons name="instagram_3" color="#BDC4CD" />
            <Icons name="youtube_3" color="#BDC4CD" />
          </div>
        </div>

        <div class="flex gap-20">
          <div>
            <h6 class="h6 mb-3">About</h6>

            <div class="body-muted flex flex-col gap-1">
              <p>About Us</p>
              <p>Find store</p>
              <p>Categories</p>
              <p>Blogs</p>
            </div>
          </div>

          <div>
            <h6 class="h6 mb-3">Partnership</h6>

            <div class="body-muted flex flex-col gap-1">
              <p>About Us</p>
              <p>Find store</p>
              <p>Categories</p>
              <p>Blogs</p>
            </div>
          </div>

          <div>
            <h6 class="h6 mb-3">Information</h6>

            <div class="body-muted flex flex-col gap-1">
              <p>Help Center</p>
              <p>Money Refund</p>
              <p>Shipping</p>
              <p>Contact us</p>
            </div>
          </div>

          <div>
            <h6 class="h6 mb-3">For users</h6>

            <div class="body-muted flex flex-col gap-1">
              <p>Login</p>
              <p>Register</p>
              <p>Settings</p>
              <p>My Orders</p>
            </div>
          </div>
        </div>

        <div class="">
          <h6 class="h6 mb-3">Get app</h6>

          <div class="body-muted flex flex-col gap-2">
            <div class="bg-dark rounded-lg p-3">
              <img src="/icons/get-app-store.svg" alt="app-store" />
            </div>

            <div class="bg-dark rounded-lg p-3">
              <img src="/icons/get-google-play.svg" alt="app-store" />
            </div>
          </div>
        </div>
      </nav>
    </Container>

    <div class="h6 border-y-2 border-gray-300 bg-gray-200">
      <Container>
        <div class="py-5 flex items-center justify-between">
          <div class="flex items-center gap-10 body-muted">
            <span>© 2023 Ecommerce.</span>
          </div>

          <div class="flex items-center gap-10">
            <div class="flex items-center gap-2 cursor-pointer select-none">
              <span>English</span>

              <img width="24" src="/images/us.png" alt="us" />

              <Icons name="expand_less" color="#8B96A5" />
            </div>
          </div>
        </div>
      </Container>
    </div>
  </footer>
</template>

<script setup></script>

<style lang="scss" scoped></style>
