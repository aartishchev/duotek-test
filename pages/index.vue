<template>
  <div class="application">
    <header class="header">
      <div class="header__wrapper">
        <p><img src="@/assets/images/logo.svg" alt="Логотип" /></p>
        <nav>
          <ul class="header__nav-list">
            <li class="header__nav-item">Тендеры</li>
            <li class="header__nav-item">Компании</li>
            <li class="header__nav-item">Продукты</li>
            <li class="header__nav-item">Кейсы</li>
            <li class="header__nav-item">Блог</li>
          </ul>
        </nav>
        <p class="header__login">Вход и регистрация</p>
      </div>
    </header>

    <main class="companies__page">
      <h1 class="companies__heading">Каталог компаний</h1>
      <section class="companies__content">
        <form class="companies__search-form">
          <input
            class="companies__search-input"
            type="search"
            placeholder="Поиск продукта или отрасли"
          />
          <button class="companies__search-button">Найти</button>
        </form>
        <ul>
          <li class="companies__list-item">
            <h2 class="companies__item-title">Компания</h2>
            <p class="companies__item-description">Описание</p>
          </li>
          <ul>
            <li class="companies__item-label">Лейбл</li>
          </ul>
        </ul>
      </section>
      <form class="companies__filter">
        <label class="companies__filter-label" for="branch-select">
          Отрасль
        </label>
        <select id="branch-select" name="branch-filter">
          <option value="" selected>Все отрасли</option>
        </select>
        <label class="companies__filter-label" for="branch-select">
          Специализация
        </label>
        <select id="specialization-select" name="specialization-filter">
          <option value="" selected>Все специализации</option>
        </select>
      </form>
    </main>
  </div>
</template>

<script>
export default {}
</script>

<style lang="scss">
@import '@/assets/style/layout.scss';

.application {
  min-width: 320px;
}

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

.companies__page {
  @include centering-layout;
  padding-top: 75px;
  font-family: var(--font-rubik);
  display: grid;
  grid-template-columns: 1fr auto;
  gap: 18px;
}

.companies__content {
  max-width: 745px;
}

.companies__heading {
  grid-column: 1 / -1;
  font-family: var(--font-raleway);
  font-size: var(--text-2xl);
  line-height: 1.3;
  font-weight: 600;
  letter-spacing: 0.12px;
}

.companies__search-form {
  display: flex;
  position: relative;

  &::before {
    content: '';
    position: absolute;
    width: 24px;
    height: 24px;
    background-image: url('@/assets/images/search-icon.svg');
    top: 7px;
    left: 11px;
  }
}

.companies__search-input {
  font-family: var(--font-raleway);
  font-size: var(--text-base);
  line-height: 1.5;
  font-weight: 500;
  padding: 7px 8px 7px 0;
  border: 1px solid var(--gray-229);
  width: 100%;
  border-top-left-radius: var(--radius-primary);
  border-bottom-left-radius: var(--radius-primary);
  padding-left: 43px;
  outline: none;

  &::placeholder {
    color: var(--gray-128);
  }

  &:focus {
    border-color: var(--blue-primary);
  }
}

.companies__search-button {
  font-size: var(--text-small);
  padding: 0 18px;
  background-color: var(--blue-primary);
  color: white;
  border-top-right-radius: var(--radius-primary);
  border-bottom-right-radius: var(--radius-primary);
  transition: var(--opacity-transition);

  &:hover {
    opacity: var(--on-hover-opacity);
  }
}

.companies__filter {
  width: 264px;
  padding: 18px 20px;
  background-color: var(--gray-247);
  border-radius: var(--radius-primary);
}

.companies__filter-label {
}

.companies__list-item {
  padding: 0 52px 0 0;
}

.companies__item-title {
  font-size: var(--text-xl);
  line-height: 1;
  font-weight: normal;
  color: var(--blue-primary);
}

.companies__item-description {
  font-size: var(--text-small);
  line-height: 1.5;
  color: var(--gray-51);
}

.companies__item-label {
  font-size: var(--text-small);
  line-height: 1.4;
  letter-spacing: 0.12px;
  padding: 5px 22px 7px 22px;
  background-color: var(--gray-247);
  border-radius: var(--radius-chip);
}
</style>
