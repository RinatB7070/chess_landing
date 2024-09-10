<template>
  <div class="header">
    <div class="header__bg-effect"></div>
    <div class="header__content_box container">
      <img class="header__content_box__logo" src="../../public/assets/AppHeader/logo.svg" alt="logo">
      <div class="header__content_box__text_box">
        <h1 class="header__content_box__headline">превратите уездный город <br><span class="text-center">в столицу земного шара</span></h1>
        <p class="header__content_box__text">Оплатите взнос на телеграммы для организации Международного васюкинского турнира по шахматам</p>
        <div class="header__content_box__btn_box">
          <button class="header__content_box__left_btn">Поддержать шахматную мысль</button>
          <button class="header__content_box__right_btn">Подробнее о турнире</button>
        </div>
      </div>
      <img :src="require(`../../public/assets/AppHeader/${city_path}`)" alt="city" class="header__content_box__city">
    </div>
  </div>
</template>


<script>
export default {
  props: ['isMobile'],
  computed: {
    city_path () {
      if (this.isMobile) {
        return 'city_mobile.png'
      } else {
        return 'city.png'
      }
    }
  }
}
</script>