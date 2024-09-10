<template>
  <div class="meta container">
    <div class="meta_first">
      <p>Чтобы поддержать<br>Международный васюкинский<br>турнир посетите лекцию на тему:<br><span>«Плодотворная дебютная идея»</span></p>
      <img src="../../public/assets/AppMeta/meta_first.png" alt="">
    </div>
    <div class="meta_two">
      <img src="../../public/assets/AppMeta/meta_two.png" alt="">
      <div class="meta_two__content container">
        <p>и Сеанс <span>одновременной игры в шахматы на 160</span> досках гроссмейстера О. Бендера</p>
        <table class="meta_two__content__table" v-if="!this.isMobile">
            <tr>
              <td>Место проведения:</td>
              <td>Клуб «Картонажник»</td>
            </tr>
            <tr>
              <td>Дата и время мероприятия:</td>
              <td>22 июня 1927 г. в 18:00</td>
            </tr>
            <tr>
              <td>Стоимость входных билетов:</td>
              <td>20 коп.</td>
            </tr>
            <tr>
              <td>Плата за игру:</td>
              <td>50 коп.</td>
            </tr>
            <tr class="meta__preview__table__last_cell">
              <td>Взнос на телеграммы:</td>
              <td>100 руб.  21 руб. 16 коп.</td>
            </tr>
        </table>
          <ul v-else class="meta_two__content__table-mobile">
            <li>Место проведения:</li>
            <li>Клуб «Картонажник»</li>
            <li>Дата и время мероприятия: </li>
            <li>22 июня 1927 г. в 18:00</li>
            <li>Стоимость входных билетов:</li>
            <li>20 коп.</li>
            <li>Плата за игру:</li>
            <li>50 коп.</li>
            <li>Взнос на телеграммы:</li>
            <li><span>100 руб.</span> 21 руб. 16 коп.</li>
          </ul>
        <a href="#">По всем вопросам обращаться в администрацию к К. Михельсону</a>
      </div>
    </div>
  </div>
</template>


<script>
export default {
  props: ['isMobile'],
  computed: {

  }
}
</script>