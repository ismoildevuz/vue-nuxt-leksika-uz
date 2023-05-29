<template>
  <div class="w-full rounded-[18px] bg-white p-10 my-10">
    <h2 class="text-[32px] leading-[48px] font-semibold mb-5">
      {{ el.word }}
    </h2>

    <h3 class="dark-gray text-[16px] leading-[24px] mb-3">
      <i>
        {{ el?.meanings?.map((i) => i?.partOfSpeech)?.join(", ") }}
      </i>
    </h3>

    <div v-if="el?.phonetics?.find((i) => i?.audio)?.audio" class="flex items-center gap-5 mb-3">
      <div
        @click="playAudio(key)"
        class="flex items-center justify-center p-2 w-fit rounded-full hover:bg-slate-100 cursor-pointer"
      >
        <img src="../assets/icons/icon-audio.svg" alt="" />
      </div>
      <audio
        ref="audio"
        :id="key + ''"
        :src="el?.phonetics?.find((i) => i?.audio)?.audio"
      ></audio>

      <span class="dark-gray text-[18px] leading-[27px]">
        {{ el?.phonetics?.find((i) => i?.text)?.text }}
      </span>
    </div>

    <h3 class="text-[18px] leading-[27px]">
      {{
        el?.meanings
          ?.find((i) => i?.definitions?.find((j) => j?.example))
          ?.definitions?.find((e) => e?.example)?.example
      }}
    </h3>
  </div>
</template>

<script setup>
const props = defineProps(["el", "key"]);

const playAudio = (id) => {
  document.getElementById(id).play();
};
</script>

<style lang="scss" scoped>
.dark-gray {
  color: $dark-gray;
}
</style>
