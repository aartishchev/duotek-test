<template>
  <main class="home__page">
    <h1 class="home__heading">Домашняя страница</h1>
  </main>
</template>

<style lang="scss">
@import '@/assets/style/mixins.scss';

.home__page {
  @include centering-layout;
  @include page-positioning;
}

.home__heading {
  @include page-heading;
}
</style>
