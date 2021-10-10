<template>
  <main class="company__page">
    <h1 class="company__heading">{{ company.title }}</h1>

    <section>
      <h2 class="company__description-section">Описание компании</h2>
      <div class="company__stat-wrapper">
        <p class="company__stat-number">
          {{ company.age }}
          <sup class="company__stat-sup">лет</sup>
        </p>
        <p class="company__stat-number">
          {{ company.staff }}
          <sup class="company__stat-sup">человек</sup>
        </p>
      </div>
      <p>
        {{ company.description_short }}
      </p>
      <p>
        {{ company.description_full }}
      </p>
    </section>

    <h2>Проектная Специализация</h2>

    <h2>Технологии</h2>

    <NuxtLink
      to="/companies"
      class="company__back-button"
    >
      Компании
    </NuxtLink>
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
  font-family: var(--font-rubik);
  position: relative;
}

.company__heading {
  @include page-heading;
}

.company__description-section {
  @include sr-only;
}

.company__stat-wrapper {
  display: flex;
  column-gap: 20px;
}

.company__stat-number {
  color: var(--alert-primary);
  font-size: var(--text-3xl);
  line-height: 1.1;
  font-weight: 300;
  letter-spacing: 0.12px;
}

.company__stat-sup {
  color: var(--gray-51);
  font-size: var(--text-base);
  line-height: 1;
  font-weight: normal;
  letter-spacing: normal;
}

.company__back-button {
  position: absolute;
  top: 0;
}
</style>
