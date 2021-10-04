<template>
  <main class="cases__page">
    <h1 class="cases__heading">Кейсы</h1>
  </main>
</template>

<style lang="scss">
@import '@/assets/style/mixins.scss';

.cases__page {
  @include centering-layout;
  @include page-positioning;
}

.cases__heading {
  @include page-heading;
}
</style>
