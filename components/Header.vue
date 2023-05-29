<template>
  <header class=" sticky top-0 z-10">
    <Container>
      <nav class="flex items-center justify-between py-4">
        <NuxtLink to="/"
          ><img class="h-[40px]" src="../assets/icons/logo.svg" alt="logo"
        /></NuxtLink>

        <ul class="flex items-center gap-10 text-white">
          <li>
            <NuxtLink to="/articles"
              ><span class="text-[18px] leading-[27px]"
                >Articles</span
              ></NuxtLink
            >
          </li>
          <li>
            <NuxtLink to="/grammar"
              ><span class="text-[18px] leading-[27px]">Grammar</span></NuxtLink
            >
          </li>
          <li>
            <NuxtLink to="/about"
              ><span class="text-[18px] leading-[27px]"
                >About us</span
              ></NuxtLink
            >
          </li>
        </ul>
      </nav>
    </Container>
  </header>
</template>

<script setup></script>

<style lang="scss" scoped>
header {
  background: $main;
}
</style>
