<template>
  <form
    @submit.prevent
    class="absolute w-0 2xl:w-[500px] top-12 right-10 z-20 bg-white rounded-lg 2xl:p-8"
  >
    <div class="">
      <h4 class="h4 mb-5">
        <span class="">Send quote to suppliers</span>
      </h4>

      <div class="h6">
        <input
          type="text"
          name="name"
          id="name"
          placeholder="What item you need?"
          class="font-normal border-2 border-gray-300 rounded-lg p-2 w-full mb-5"
          required
        />

        <div class="relative w-full mb-5">
          <!-- <Icons
                  class="absolute bottom-0 -right-1 rotate-45"
                  name="arrow_right"
                  color="#E4E4E4"
                /> -->
          <textarea
            name="details"
            id="details"
            rows="3"
            class="font-normal border-2 border-gray-300 rounded-lg p-2 w-full max-h-[100px] min-h-[50px]"
            placeholder="Type more details"
            required
          ></textarea>
        </div>

        <div class="flex gap-5 items-center mb-5">
          <input
            type="number"
            placeholder="Quantity"
            class="font-normal border-2 border-gray-300 rounded-lg p-2 w-[200px]"
            required
          />

          <div class="relative">
            <Icons
              class="absolute top-[25%] right-2"
              name="expand_more"
              color="#8B96A5"
            />
            <select
              name="pcs"
              id="pcs"
              class="font-normal border-2 border-gray-300 rounded-lg p-2 w-[150px] appearance-none"
              required
            >
              <option selected hidden disabled>Pcs</option>
              <option>item 1</option>
              <option>item 2</option>
              <option>item 3</option>
            </select>
          </div>
        </div>
      </div>

      <button type="submit" class="px-4 py-3 bg-primary rounded-lg">
        <span class="text-white font-medium"> Send inquiry </span>
      </button>
    </div>
  </form>
</template>

<script setup>
const props = defineProps(["el"]);
</script>

<style lang="scss" scoped></style>
