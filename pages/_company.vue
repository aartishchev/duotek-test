<template>
  <main class="company__page">
    <NuxtLink to="/companies" class="company__back-button">Компании</NuxtLink>
    <h1 class="company__heading">{{ company.title }}</h1>
  </main>

</template>

<script>
import companies from '@/static/companies.json'

export default {
  asyncData({ params }) {
    const company = companies.data.find((el) => el.ident === params.company)
    return { company }
  }
}
</script>

<style lang="scss">
@import '@/assets/style/mixins.scss';

.company__page {
  @include centering-layout;
  @include page-positioning;
  position: relative;
}

.company__heading {
  @include page-heading;
}

.company__back-button {
  position: absolute;
  top: 0;
  }
</style>
