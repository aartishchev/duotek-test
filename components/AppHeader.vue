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
          <li class="header__nav-item">
            <NuxtLink to="/tenders">Тендеры</NuxtLink>
          </li>
          <li class="header__nav-item">
            <NuxtLink to="/companies">Компании</NuxtLink>
          </li>
          <li class="header__nav-item">
            <NuxtLink to="/products">Продукты</NuxtLink>
          </li>
          <li class="header__nav-item">
            <NuxtLink to="/cases">Кейсы</NuxtLink>
          </li>
          <li class="header__nav-item">
            <NuxtLink to="/blog">Блог</NuxtLink>
          </li>
        </ul>
      </nav>

      <p class="header__login">
        <NuxtLink to="/login">Вход и регистрация</NuxtLink>
      </p>
    </div>
  </header>
</template>

<script>
export default {}
</script>

<style lang="scss">
@import '@/assets/style/layout.scss';

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

.header__nav-item,
.header__login {
  color: var(--blue-primary);
  padding: 8px;
  transition: var(--opacity-transition);

  &:hover {
    opacity: var(--on-hover-opacity);
  }
}

.header__login {
  justify-self: end;
}
</style>
