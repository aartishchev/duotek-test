<template>
  <main class="products__page">
    <h1 class="products__heading">Продукты</h1>
  </main>
</template>

<style lang="scss">
@import '@/assets/style/mixins.scss';

.products__page {
  @include centering-layout;
  @include page-positioning;
}

.products__heading {
  @include page-heading;
}
</style>
