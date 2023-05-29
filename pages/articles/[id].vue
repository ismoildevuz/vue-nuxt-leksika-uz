<template>
  <section class="articles py-10">
    <Container>
      <div class="wrapper flex">
        <div class="w-[60%]">
          <div v-if="article" class="w-full rounded-[18px] bg-white p-10 mb-5">
            <h1
              class="text-[32px] leading-[48px] font-semibold text-center mb-5"
            >
              {{ article.title }}
            </h1>

            <h2 class="text-[16px] leading-[24px] mb-5">{{ article.body }}</h2>

            <div
              class="rounded-[18px] overflow-hidden flex items-center justify-center"
            >
              <img
                class="w-full"
                src="../../assets/images/card-image.png"
                alt="image"
              />
            </div>
          </div>

          <div
            v-if="article"
            class="w-full rounded-[18px] bg-white px-10 py-5 flex justify-between"
          >
            <div class="card-info flex gap-10">
              <div class="flex items-center gap-2">
                <img src="../../assets/icons/card-date.svg" alt="" />
                <h4 class="">
                  {{ article.createdAt.split("T")[0] }}
                </h4>
              </div>

              <div class="flex items-center gap-2">
                <img src="../../assets/icons/card-read.svg" alt="" />
                <h4 class="">number of reads: {{ article.reads }}</h4>
              </div>
            </div>

            <div class="flex gap-5 items-center">
              <button>
                <img src="../../assets/icons/share-telegram.svg" alt="" />
              </button>
              <button>
                <img src="../../assets/icons/share-facebook.svg" alt="" />
              </button>
              <button>
                <img src="../../assets/icons/share-instagram.svg" alt="" />
              </button>
              <button>
                <img src="../../assets/icons/share-twitter.svg" alt="" />
              </button>
            </div>
          </div>
        </div>

        <div class="w-[40%]">
          <LatestArticles />
        </div>
      </div>
    </Container>
  </section>
</template>

<script setup>
import { articles } from "../../constants/articles";

const { id } = useRoute().params;

const article = articles.find((el) => el.id == id);

if (!article) {
  throw createError({
    statusMessage: "Article not found",
    statusCode: 404,
  });
}
</script>

<style lang="scss" scoped>
.card-info {
  color: $dark-gray;
}
</style>
