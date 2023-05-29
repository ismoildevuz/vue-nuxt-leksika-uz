<template>
  <footer class="">
    <Container>
      <div class="flex items-center justify-between py-10 text-white">
        <span class="block text-[18px] leading-[27px]"
          >Leksika.uz - 2022-2023</span
        >

        <ul class="flex items-center gap-10">
          <li>
            <NuxtLink to="/"
              ><img src="../assets/icons/link-telegram.svg" alt="link"
            /></NuxtLink>
          </li>
          <li>
            <NuxtLink to="/"
              ><img src="../assets/icons/link-instagram.svg" alt="link"
            /></NuxtLink>
          </li>
          <li>
            <NuxtLink to="/"
              ><img src="../assets/icons/link-facebook.svg" alt="link"
            /></NuxtLink>
          </li>
          <li>
            <NuxtLink to="/"
              ><img src="../assets/icons/link-youtube.svg" alt="link"
            /></NuxtLink>
          </li>
          <li>
            <NuxtLink to="/"
              ><img src="../assets/icons/link-twitter.svg" alt="link"
            /></NuxtLink>
          </li>
        </ul>
      </div>
    </Container>
  </footer>
</template>

<script setup></script>

<style lang="scss" scoped>
footer {
  background: $main;
}
</style>
