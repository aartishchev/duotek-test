<template>
  <main class="login__page">
    <h1 class="login__heading">Авторизация</h1>
  </main>
</template>

<style lang="scss">
@import '@/assets/style/mixins.scss';

.login__page {
  @include centering-layout;
  @include page-positioning;
}

.login__heading {
  @include page-heading;
}
</style>
