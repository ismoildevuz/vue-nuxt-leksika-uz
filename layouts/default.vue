<template>
  <Header />
  <main class="min-h-screen">
    <slot />
  </main>
  <Footer />
</template>

<script setup></script>

<style lang="scss" scoped>
main {
  background: $background;
}
</style>
