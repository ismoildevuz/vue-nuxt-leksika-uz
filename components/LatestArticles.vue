<template>
  <div class=" sticky top-[115px] w-full px-10">
    <h2 class="text-[24px] leading-[36px] font-semibold mb-5">
      Latest articles
    </h2>

    <div class="w-full rounded-[18px] p-5 bg-white mb-5">
      <ul>
        <li v-for="(el, ind) in articles">
          <NuxtLink
            :to="`/articles/${el.id}`"
            class="flex items-center gap-2 my-4 hover:underline"
            ><div class="w-[10px] h-[10px] bg-gray-300 rounded-full"></div>
            {{ el.title.slice(0, 55) }} ...</NuxtLink
          >
        </li>
      </ul>
    </div>

    <h2 class="text-[24px] leading-[36px] font-semibold mb-5">Tags</h2>

    <div class="w-full">
      <div v-for="(el, ind) in tags" :key="ind" class="inline-block rounded-full bg-white px-5 py-3 mb-4 mr-4 cursor-pointer hover:bg-slate-50">
        <span class="text-[16px] leading-[24px]">{{el.name}}({{ el.count }})</span>
      </div>
    </div>
  </div>
</template>

<script setup>
import { articles } from "../constants/articles";
import { tags } from "../constants/tags";
</script>

<style lang="scss" scoped>
li,
span {
  color: $gray;
}
</style>
