<template>
  <section class="bg-gray-100">
    <Container class="py-10">
      <h3 class="h3 mb-10">
        <span>My cart ({{ cart.length }})</span>
      </h3>

      <div class="flex gap-5">
        <div class="w-full border-2 border-gray-300 rounded-lg p-5 bg-white">
          <div
            v-for="(el, ind) in cart"
            :key="ind"
            class="border-b-2 pb-5 mb-5 flex gap-5"
          >
            <div class="flex-shrink-0">
              <img
                class="w-[80px] h-[80px] object-cover border-2 rounded-lg"
                :src="`/images/${el.image}`"
                alt="cart"
              />
            </div>

            <div class="flex justify-between w-full">
              <div>
                <h5 class="h5 mb-5">
                  <span>{{ el.name }}</span>
                </h5>

                <div class="body-muted mb-5">
                  <h6>
                    <span>{{ el.description }}</span>
                  </h6>
                  <h6>
                    <span>{{ el.seller }}</span>
                  </h6>
                </div>

                <div class="flex gap-5">
                  <button class="py-1 px-2 border-2 rounded-lg text-red">
                    <span>Remove</span>
                  </button>

                  <button class="py-1 px-2 border-2 rounded-lg text-primary">
                    <span>Save for later</span>
                  </button>
                </div>
              </div>

              <div class="flex flex-col items-end">
                <h5 class="h5 mb-5">
                  <span>{{ el.price }}</span>
                </h5>

                <div class="relative">
                  <Icons
                    class="absolute top-[25%] right-2"
                    name="expand_more"
                    color="#8B96A5"
                  />
                  <select
                    v-model="el.quantity"
                    name="pcs"
                    id="pcs"
                    class="font-normal border-2 border-gray-300 rounded-lg p-2 w-[120px] appearance-none"
                  >
                    <option :value="el.quantity" selected hidden disabled>
                      Qty: {{ el.quantity }}
                    </option>
                    <option value="1">Qty: 1</option>
                    <option value="2">Qty: 2</option>
                    <option value="3">Qty: 3</option>
                  </select>
                </div>
              </div>
            </div>
          </div>
          <div class="flex justify-between p-5 h6">
            <nuxt-link
              to="/"
              class="py-3 px-4 border-2 rounded-lg flex gap-5 items-center bg-primary"
            >
              <Icons name="arrow_back" color="white" />
              <span class="text-white">Back to shop</span>
            </nuxt-link>

            <button class="py-3 px-4 border-2 rounded-lg">
              <span class="text-primary">Remove all</span>
            </button>
          </div>
        </div>

        <div class="flex-shrink-0 w-[300px]">
          <div
            class="border-2 border-gray-300 rounded-lg overflow-hidden bg-white p-5"
          >
            <h6 class="body mb-5"><span>Have a coupon?</span></h6>

            <div class="flex border-2 overflow-hidden rounded-lg">
              <input
                class="p-2 focus:outline-none w-full"
                type="text"
                placeholder="Add coupon"
              />

              <button class="h6 py-3 px-4 border-l-2">
                <span class="font-medium text-primary">Apply</span>
              </button>
            </div>
          </div>

          <div
            class="border-2 border-gray-300 rounded-lg overflow-hidden bg-white p-5 mt-5"
          >
            <div class="body pb-3 border-b-2">
              <div class="flex justify-between mb-2">
                <h6><span>Subtotal:</span></h6>
                <h6><span>$1403.97</span></h6>
              </div>

              <div class="flex justify-between mb-2">
                <h6><span>Discount:</span></h6>
                <h6 class="text-red"><span>- $60.00</span></h6>
              </div>

              <div class="flex justify-between mb-2">
                <h6><span>Tax:</span></h6>
                <h6 class="text-green"><span>+ $14.00</span></h6>
              </div>
            </div>

            <div class="pt-5">
              <div class="flex justify-between mb-3">
                <h6 class="h6"><span>Total:</span></h6>
                <h4 class="h4"><span>$1357.97</span></h4>
              </div>

              <button
                class="h5 py-4 flex items-center justify-center bg-green rounded-lg w-full"
              >
                <span class="font-medium text-white">Checkout</span>
              </button>

              <div class="flex justify-center gap-2 mt-5">
                <div
                  v-for="(el, ind) in card"
                  :key="ind"
                  class="border-2 rounded py-1 flex items-center justify-center w-[140px]"
                >
                  <img :src="`/icons/${el.logo}`" />
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>

      <div class="py-10 flex gap-16">
        <div class="flex gap-3 items-center">
          <div
            class="flex items-center justify-center p-4 bg-gray-300 rounded-full"
          >
            <Icons name="lock_fill" color="#8B96A5" size="20" />
          </div>

          <div>
            <h6 class="body">
              <span class="text-dark">Secure payment</span>
            </h6>
            <h6 class="body">
              <span class="text-gray-400">Have you ever finally just </span>
            </h6>
          </div>
        </div>

        <div class="flex gap-3 items-center">
          <div
            class="flex items-center justify-center p-4 bg-gray-300 rounded-full"
          >
            <Icons name="chat_fill" color="#8B96A5" size="20" />
          </div>

          <div>
            <h6 class="body">
              <span class="text-dark">Customer support</span>
            </h6>
            <h6 class="body">
              <span class="text-gray-400">Have you ever finally just </span>
            </h6>
          </div>
        </div>

        <div class="flex gap-3 items-center">
          <div
            class="flex items-center justify-center p-4 bg-gray-300 rounded-full"
          >
            <Icons name="delivery" color="#8B96A5" size="20" />
          </div>

          <div>
            <h6 class="body">
              <span class="text-dark">Free delivery</span>
            </h6>
            <h6 class="body">
              <span class="text-gray-400">Have you ever finally just </span>
            </h6>
          </div>
        </div>
      </div>

      <div class="bg-white border-2 border-gray-300 rounded-lg p-5">
        <h4 class="h4 mb-5"><span>Saved for later</span></h4>

        <div class="flex justify-between">
          <div
            v-for="(el, ind) in saved"
            :key="ind"
            class="bg-white rounded-lg overflow-hidden"
          >
            <div
              class="flex justify-center items-center rounded-lg overflow-hidden border-2 mb-5"
            >
              <img
                class="w-[270px] h-[240px] object-cover"
                :src="`/images/${el.image}`"
                alt="saved"
              />
            </div>

            <div class="py-5">
              <div>
                <h5 class="h5 mb-2">
                  <span>{{ el.price }}</span>
                </h5>
              </div>

              <h6 class="body w-[240px]">
                <span>{{ el.description }}</span>
              </h6>
            </div>

            <button
              class="h6 py-2 px-3 border-2 rounded-lg flex items-center gap-3"
            >
              <Icons name="shopping_cart" color="#0D6EFD" />

              <span class="text-primary">Move to cart</span>
            </button>
          </div>
        </div>
      </div>

      <div class="relative rounded-lg overflow-hidden my-5">
        <img class="w-full h-[120px] object-cover" src="/icons/bg-cover.svg" />

        <div class="absolute top-7 left-7">
          <h3 class="h3 mb-2">
            <span class="text-white">Super discount on more than 100 USD</span>
          </h3>
          <h6 class="h6 opacity-70">
            <span class="text-white font-normal"
              >Have you ever finally just write dummy info</span
            >
          </h6>
        </div>

        <div class="absolute top-10 right-7">
          <button class="bg-orange rounded-lg py-2 px-3">
            <span class="text-white"> Shop now </span>
          </button>
        </div>
      </div>
    </Container>
  </section>
</template>

<script setup>
const saved = ref([
  {
    id: 1,
    image: "mobile-image-4.png",
    price: "$99.50",
    description: "GoPro HERO6 4K Action Camera - Black",
  },

  {
    id: 2,
    image: "mobile-image-2.png",
    price: "$99.50",
    description: "GoPro HERO6 4K Action Camera - Black",
  },

  {
    id: 3,
    image: "mobile-image-8.png",
    price: "$99.50",
    description: "GoPro HERO6 4K Action Camera - Black",
  },

  {
    id: 4,
    image: "mobile-image-7.png",
    price: "$99.50",
    description: "GoPro HERO6 4K Action Camera - Black",
  },
]);

const card = ref([
  {
    id: 1,
    logo: "card-american-express.svg",
  },
  {
    id: 2,
    logo: "card-mastercard.svg",
  },
  {
    id: 3,
    logo: "card-pay-pal.svg",
  },
  {
    id: 4,
    logo: "card-visa.svg",
  },
  {
    id: 5,
    logo: "card-apple-pay.svg",
  },
]);

const cart = ref([
  {
    id: 1,
    image: "cart-image-1.png",
    name: "T-shirts with multiple colors, for men and lady",
    description: "Size: medium, Color: blue,  Material: Plastic",
    seller: "Seller: Artel Market",
    price: "$78.99",
    quantity: "9",
  },
  {
    id: 2,
    image: "cart-image-2.png",
    name: "T-shirts with multiple colors, for men and lady",
    description: "Size: medium, Color: blue,  Material: Plastic",
    seller: "Seller: Best factory LLC",
    price: "$39.00",
    quantity: "3",
  },
  {
    id: 3,
    image: "cart-image-3.png",
    name: "T-shirts with multiple colors, for men and lady",
    description: "Size: medium, Color: blue,  Material: Plastic",
    seller: "Seller: Artel Market",
    price: "$170.50",
    quantity: "1",
  },
]);

definePageMeta({
  layout: "cart",
});
</script>

<style lang="scss" scoped></style>
