<template>
  <main class="company__page">
    <h1 class="company__heading">{{ company.title }}</h1>

    <section class="company__description-section">
      <h2 class="company__description-heading">Описание компании</h2>

      <div class="company__stat-wrapper">
        <p class="company__stat-number">{{ company.age }}</p>
        <sup class="company__stat-sup">лет</sup>
        <p class="company__stat-number">{{ company.staff }}</p>
        <sup class="company__stat-sup">человек</sup>
      </div>

      <p class="company__description-short">
        {{ company.description_short }}
      </p>

      <p class="company__description-full">
        {{ company.description_full }}
      </p>
    </section>

    <section
      v-if="company.companySpecializations.length > 0"
      class="company__specializations-section"
    >
      <h2 class="company__specialization-heading">Проектная cпециализация</h2>
      <ul class="company__info-chips-list">
        <li
          v-for="specialization in company.companySpecializations"
          :key="specialization.id"
          class="company__info-chip"
        >
          {{ specialization.title }}
        </li>
      </ul>
    </section>

    <section
      v-if="company.industries.length > 0"
      class="company__industries-section"
    >
      <h2 class="company__industries-heading">Технологии</h2>
      <ul class="company__info-chips-list">
        <li
          v-for="industry in company.industries"
          :key="industry.id"
          class="company__info-chip"
        >
          {{ industry.title }}
        </li>
      </ul>
    </section>

    <NuxtLink to="/companies" class="company__back-button">
      <img src="@/assets/images/arrow-icon-left.svg" alt="Вернуться назад" />
      <span>Компании</span>
    </NuxtLink>
  </main>
</template>

<script>
import companies from '@/static/companies.json'

export default {
  asyncData({ params }) {
    const company = companies.data.find((el) => el.ident === params.company)
    return { company }
  },
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

.company__description-section,
.company__specializations-section {
  margin-bottom: 40px;
}

.company__description-heading {
  @include sr-only;
}

.company__stat-wrapper {
  display: flex;
  margin-bottom: 10px;
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
  padding-top: 8px;
}

.company__description-short {
  color: var(--gray-51);
  font-size: var(--text-large);
  line-height: 1.4;
  margin-bottom: 24px;
}

.company__description-full {
  color: var(--gray-51);
  font-size: var(--text-small);
  line-height: 1.5;
}

.company__specialization-heading,
.company__industries-heading {
  color: var(--gray-51);
  font-size: var(--text-large);
  line-height: 1;
  margin-bottom: 24px;
}

.company__info-chips-list {
  @include info-chips-list;
}

.company__info-chip {
  @include info-chip;
  color: var(--gray-72);
}

.company__back-button {
  position: absolute;
  top: 39px;
  display: flex;
  align-items: center;
  column-gap: 11px;
  color: var(--blue-primary);
  transition: var(--transition-ease);

  & span {
    font-size: var(--text-small);
    line-height: 1;
  }

  &:hover {
    opacity: var(--on-hover-opacity);
  }
}
</style>
