<template>
  <div
    class="w-full flex items-center gap-[20px] p-1 bg-white rounded-full focus-within:outline focus-within:outline-[1px] focus-within:outline-[#a098ae]"
  >
    <div
      class="change-lang flex items-center gap-2 rounded-full py-2 px-5 cursor-pointer text-white text-[16px] leading-[24px]"
    >
      <div>
        <span>ENG</span>
      </div>
      <div class="flex items-center justify-center w-6 h-6">
        <img src="../assets/icons/change-lang.svg" alt="" />
      </div>
      <div>
        <span>UZB</span>
      </div>
    </div>

    <div class="flex items-center">
      <img src="../assets/icons/search-logo.svg" />
    </div>

    <form @submit.prevent="$emit('search', searching)" class="flex w-full items-center">
      <input
        v-model="searching"
        type="text"
        :placeholder="placeholder"
        class="text-[16px] leading-[24px] focus:outline-none w-full"
      />

      <button
        type="reset"
        v-if="searching"
        class="flex items-center justify-center p-2 hover:bg-slate-100 cursor-pointer rounded-full focus:outline-none"
      >
        <img src="../assets/icons/icon-cancel.svg" alt="" />
      </button>
    </form>
  </div>
</template>

<script setup>
const searching = ref("");

const props = defineProps(["placeholder"]);
</script>

<style lang="scss" scoped>
.change-lang {
  background: $main;
}
</style>
