<template>
  <component :is="tag" class="companies__item">
    <NuxtLink :to="company.ident" class="companies__item-link">
      <img :src="company.picture" alt="Логотип компании" />
      <div>
        <h2 class="companies__title">{{ company.title }}</h2>
        <p class="companies__description">{{ company.description_short }}</p>
        <ul class="companies__info-chips-list">
          <li
            v-for="specialization in companySpecializations"
            :key="specialization.id"
            class="companies__info-chip"
          >
            {{ specialization.title }}
          </li>
        </ul>
      </div>
    </NuxtLink>
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
    }
  },
  data() {
    return {
      companySpecializations: this.company.companySpecializations,
    }
  },
}
</script>

<style lang="scss">
@import '@/assets/style/mixins.scss';

.companies__item {
  min-height: 200px;
  padding: 40px 52px 32px 9px;
  box-sizing: border-box;
  position: relative;
  transition: var(--transition-ease);

  &::before {
    content: '';
    width: 24px;
    height: 24px;
    position: absolute;
    background: url('@/assets/images/arrow-icon-right.svg') no-repeat;
    right: 15px;
    bottom: 18px;
    display: none;
  }

  &:hover {
    background-color: var(--gray-247);
  }

  &:hover .companies__title {
    color: var(--alert-primary);
  }

  &:hover .companies__info-chip {
    background-color: white;
  }

  &:hover::before {
    display: block;
  }
}

.companies__item-link {
  display: grid;
  grid-template-columns: 160px 1fr;
  column-gap: 9px;
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

.companies__info-chips-list {
  @include info-chips-list;
}

.companies__info-chip {
  @include info-chip;
  color: var(--gray-51);
}
</style>
