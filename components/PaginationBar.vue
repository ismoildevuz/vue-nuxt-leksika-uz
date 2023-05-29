<template>
  <div
    class="w-full bg-white rounded-full flex items-center justify-center gap-14 p-3"
  >
    <div
      class="pagination-text flex items-center gap-3 px-3 py-2 rounded-full cursor-pointer hover:bg-slate-100"
    >
      <img src="../assets/icons/pagination-prev.svg" alt="" />
      <span class="text-[16px] leading-[24px]">PREV</span>
    </div>

    <div class="flex gap-5">
      <div
        class="active rounded-full w-[48px] h-[48px] flex items-center justify-center cursor-pointer hover:bg-slate-100"
      >
        <span class="text-[16px] leading-[24px]">1</span>
      </div>
      <div
        class="rounded-full w-[48px] h-[48px] flex items-center justify-center cursor-pointer hover:bg-slate-100"
      >
        <span class="text-[16px] leading-[24px]">2</span>
      </div>
      <div
        class="rounded-full w-[48px] h-[48px] flex items-center justify-center cursor-pointer hover:bg-slate-100"
      >
        <span class="text-[16px] leading-[24px]">3</span>
      </div>
    </div>

    <div
      class="pagination-text flex items-center gap-3 px-3 py-2 rounded-full cursor-pointer hover:bg-slate-100"
    >
      <span class="text-[16px] leading-[24px]">NEXT</span>
      <img src="../assets/icons/pagination-next.svg" alt="" />
    </div>
  </div>
</template>

<script setup></script>

<style lang="scss" scoped>
.active {
  background: $main;
  color: white;
}

.active:hover {
  background: #006b62;
}

.pagination-text {
  color: $dark-gray;
}
</style>
