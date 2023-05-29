<template>
  <div
    class="w-full flex items-center gap-[20px] h-[60px] px-[20px] py-[10px] bg-white rounded-[18px] focus-within:outline focus-within:outline-[1px] focus-within:outline-[#a098ae]"
  >
    <div class="flex items-center">
      <img src="../assets/icons/search-logo.svg" />
    </div>

    <input
      v-model="searching"
      type="text"
      :placeholder="placeholder"
      class="text-[16px] leading-[24px] focus:outline-none w-full"
    />
  </div>
</template>

<script setup>
const searching = ref("");

const props = defineProps(["placeholder"]);
</script>

<style lang="scss" scoped></style>
