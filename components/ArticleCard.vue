<template>
  <NuxtLink
    :to="`/articles/${id}`"
    class="w-full my-5 p-5 bg-white rounded-[18px] flex custom-shadow"
  >
    <div
      class="w-[40%] h-[225px] rounded-[18px] overflow-hidden flex items-center justify-center"
    >
      <img class="w-full" src="../assets/images/card-image.png" alt="image" />
    </div>

    <div class="w-[60%] px-5">
      <div class="card-info flex gap-10">
        <div class="flex items-center gap-2">
          <img src="../assets/icons/card-date.svg" alt="" />
          <h4 class="">
            {{ createdAt.split("T")[0] }}
          </h4>
        </div>

        <div class="flex items-center gap-2">
          <img src="../assets/icons/card-read.svg" alt="" />
          <h4 class="">number of reads: {{ reads }}</h4>
        </div>
      </div>

      <h2 class="text-[24px] leading-[36px] font-semibold mb-3">{{ title }}</h2>

      <h3 class="text-[16px] leading-[24px]">{{ body.slice(0, 200) }}...</h3>
    </div>
  </NuxtLink>
</template>

<script setup>
const props = defineProps(["id", "title", "body", "createdAt", "reads"]);
</script>

<style lang="scss" scoped>
.card-info {
  color: $dark-gray;
}

.custom-shadow:hover {
  box-shadow: 0 2px 18px 3px rgba(0, 0, 0, 0.05);
}
</style>
