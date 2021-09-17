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

    <main class="main-block">
      <section>
        <h1 class="companies__heading">Каталог компаний</h1>
        <input type="search" placeholder="Поиск продукта или отрасли" />
      </section>
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
  border-bottom: 1px solid var(--border-primary);
  box-sizing: border-box;
  font-family: 'Rubik', 'Arial', sans-serif;
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
  @include text-base;
  color: var(--blue-primary);
  padding: 8px;

  &:hover {
    opacity: 30%;
  }
}

.header__login {
  justify-self: end;
}

.main-block {
  @include centering-layout;
  padding-top: 75px;
}

.companies__heading {
  @include text-2xl;
  font-family: 'Raleway', 'Arial', sans-serif;
  font-weight: 600;
  letter-spacing: 0.12px;
}
</style>
