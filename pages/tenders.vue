<template>
  <main class="tenders__page">
    <h1 class="tenders__heading">Тендеры</h1>
  </main>
</template>

<style lang="scss">
@import '@/assets/style/mixins.scss';

.tenders__page {
  @include centering-layout;
  @include page-positioning;
}

.tenders__heading {
  @include page-heading;
}
</style>
