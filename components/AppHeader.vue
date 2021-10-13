<template>
  <header class="header">
    <div class="header__wrapper">
      <p>
        <NuxtLink to="/">
          <img src="@/assets/images/logo.svg" alt="Логотип" />
        </NuxtLink>
      </p>

      <nav>
        <ul class="header__nav-list">
          <li>
            <NuxtLink to="/tenders" class="header__nav-link">Тендеры</NuxtLink>
          </li>
          <li>
            <NuxtLink to="/companies" class="header__nav-link">
              Компании
            </NuxtLink>
          </li>
          <li>
            <NuxtLink to="/products" class="header__nav-link">
              Продукты
            </NuxtLink>
          </li>
          <li>
            <NuxtLink to="/cases" class="header__nav-link">Кейсы</NuxtLink>
          </li>
          <li>
            <NuxtLink to="/blog" class="header__nav-link">Блог</NuxtLink>
          </li>
        </ul>
      </nav>

      <p class="header__login">
        <NuxtLink to="/login" class="header__nav-link"
          >Вход и регистрация</NuxtLink
        >
      </p>
    </div>
  </header>
</template>

<script>
export default {}
</script>

<style lang="scss">
@import '@/assets/style/mixins.scss';

.header {
  height: 96px;
  border-bottom: 1px solid var(--gray-242);
  box-sizing: border-box;
  font-family: var(--font-rubik);
}

.header__wrapper {
  @include centering-layout;
  display: grid;
  grid-template-columns: 1fr auto 1fr;
  column-gap: 26px;
  align-items: center;
  height: 100%;
}

.header__nav-list {
  display: flex;
  column-gap: 26px;
}

.header__nav-link {
  color: var(--blue-primary);
  padding: 8px;
  transition: var(--transition-ease);

  &:hover,
  &.nuxt-link-active {
    opacity: var(--on-hover-opacity);
  }
}

.header__login {
  justify-self: end;
}
</style>
