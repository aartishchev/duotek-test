<template>
  <main class="blog__page">
    <h1 class="blog__heading">Блог</h1>
  </main>
</template>

<style lang="scss">
@import '@/assets/style/mixins.scss';

.blog__page {
  @include centering-layout;
  @include page-positioning;
}

.blog__heading {
  @include page-heading;
}
</style>
