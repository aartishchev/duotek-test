<template>
  <component :is="tag" class="companies__item">
    <img :src="company.picture" alt="Логотип компании" />
    <div class="companies__info-wrapper">
      <h2 class="companies__title">{{ company.title }}</h2>
      <p class="companies__description">{{ company.description_short }}</p>
      <ul class="companies__label-list">
        <li
          v-for="specialization in companySpecializations"
          :key="specialization.id"
          class="companies__label"
        >
          {{ specialization.title }}
        </li>
      </ul>
    </div>
  </component>
</template>

<script>
export default {
  props: {
    tag: {
      type: String,
      default: 'li',
    },
    company: {
      type: Object,
      required: true,
    },
  },
  data() {
    return {
      companySpecializations: this.company.companySpecializations,
    }
  },
}
</script>

<style lang="scss">
.companies__item {
  display: grid;
  grid-template-columns: 160px 1fr;
  column-gap: 9px;
  min-height: 200px;
  padding: 40px 52px 32px 9px;
  box-sizing: border-box;
  position: relative;
  transition: var(--transition-ease);

  &::before {
    content: "";
    width: 24px;
    height: 24px;
    position: absolute;
    background: url('@/assets/images/arrow-icon.svg') no-repeat;
    right: 15px;
    bottom: 18px;
    visibility: hidden;
  }

  &:hover {
    background-color: var(--gray-247);
  }

  &:hover .companies__title {
    color: var(--alert-primary);
  }

  &:hover .companies__label {
    background-color: white;
  }

  &:hover::before {
    visibility: visible;
  }
}

.companies__title {
  font-size: var(--text-xl);
  line-height: 1;
  font-weight: normal;
  color: var(--blue-primary);
  margin-bottom: 16px;
}

.companies__description {
  font-size: var(--text-small);
  line-height: 1.5;
  color: var(--gray-51);
  margin-bottom: 16px;
}

.companies__label-list {
  display: flex;
  flex-wrap: wrap;
  column-gap: 4px;
}

.companies__label {
  font-size: var(--text-small);
  line-height: 1.4;
  letter-spacing: 0.12px;
  padding: 5px 22px 7px 22px;
  background-color: var(--gray-247);
  border-radius: var(--radius-chip);
}
</style>
