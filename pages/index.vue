<template>
  <main class="home__page">
    <h1 class="home__heading">Домашняя страница</h1>
  </main>
</template>

<style lang="scss">
@import '@/assets/style/layout.scss';

.home__page {
  @include centering-layout;
  padding-top: 75px;
}

.home__heading {
  font-family: var(--font-raleway);
  font-size: var(--text-2xl);
  line-height: 1.3;
  font-weight: 600;
  letter-spacing: 0.12px;
}
</style>
