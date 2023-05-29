<template>
  <section class="articles py-10">
    <Container>
      <div class="wrapper flex">
        <div class="w-[60%]">
          <SearchBox :placeholder="'Search articles here...'" />

          <div class="">
            <ArticleCard
              v-for="(el, ind) in articles"
              :key="ind"
              :id="el.id"
              :title="el.title"
              :body="el.body"
              :createdAt="el.createdAt"
              :reads="el.reads"
            />
          </div>

          <PaginationBar />
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
</script>

<style lang="scss" scoped></style>
