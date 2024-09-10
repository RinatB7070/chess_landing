<template>
  <div class="info container">
    <h1 class="info__header">Этапы преображения<br>Васюков <a href="#">Будущие источники<br>обогащения васюкинцев</a></h1>
    <ul v-if="!isMobile" class="info__table">
      <li v-for="item in info_text"
        ><img 
        :src="require(`../../public/assets/AppInfo/number${ item.id }.png`)"
        class="info_num"
        >
        {{ item.text }}
        <div
          v-if="item.addit_img"
          class="img_block"></div>
        <img 
          v-if="item.addit_img" 
          :src="require(`../../public/assets/AppInfo/${item.addit_img_path}`)"
          class="info_addit_img">
      </li>
    </ul>
    <div v-else class="info_table-mobile">
      <img src="../../public/assets/AppInfo/plane-mobile.png" alt="plane" class="info_table-mobile-plane">
      <div class="info_table-mobile-wrapper">
        <div class="info_table-mobile-inner"  :style="{'margin-left': '-' + (455 * (infoCounter)) + 'px'}">
          <div class="info_table-mobile-item double-info">
            <div>
              <img src="../../public/assets/AppInfo/number1.png" alt="number" class="info_num">
              <p>{{ this.info_text[0].text }}</p>
            </div>
            <div>
              <img src="../../public/assets/AppInfo/number2.png" alt="number" class="info_num">
              <p>{{ this.info_text[1].text }}</p>
            </div>
          </div>
          <div class="info_table-mobile-item">
            <img src="../../public/assets/AppInfo/number3.png" alt="number" class="info_num">
            <p>{{ this.info_text[2].text }}</p>
          </div>
          <div class="info_table-mobile-item double-info">
            <div>
              <img src="../../public/assets/AppInfo/number4.png" alt="number" class="info_num">
              <p>{{ this.info_text[3].text }}</p>
            </div>
            <div>
              <img src="../../public/assets/AppInfo/number5.png" alt="number" class="info_num">
              <p>{{ this.info_text[4].text }}</p>
            </div>
          </div>
          <div class="info_table-mobile-item">
            <img src="../../public/assets/AppInfo/number6.png" alt="number" class="info_num">
            <p>{{ this.info_text[5].text }}</p>
          </div>
          <div class="info_table-mobile-item">
            <img src="../../public/assets/AppInfo/number7.png" alt="number" class="info_num">
            <p>{{ this.info_text[6].text }}</p>
          </div> 
        </div>
      </div>
      <div class="info_table-mobile__buttons" data-one="hello" ref="img" >
        <button
          :class="btn_left_style"
          @click="moveInfoLeft"
          :disabled="btn_left_disabled"
        ></button>
        <div class="info_counter">
          <img 
            v-for="item in img_ids"
            :src="require(`../../public/assets/AppInfo/${changeState(item)}`)"
            alt="dot"
            :id="item"
            class="dot_img"
            >
        </div>
        <button
          :class="btn_right_style"
          @click="moveInfoRight"
          :disabled="btn_right_disabled"
        ></button>
      </div>
    </div>
  </div>
</template>


<script>
export default {
  props: ['isMobile'],
  data() {
    return {
      infoCounter: 0,
      info_text: [
        {text: 'Строительство железнодорожной магистрали Москва-Васюки',
        id: 1,
        addit_img: false
      },
        {text: 'Открытие фешенебельной гостиницы «Проходная пешка» и других небоскрёбов',
        id: 2,
        addit_img: false
      },
        {text: 'Поднятие сельского хозяйства в радиусе на тысячу километров: производство овощей, фруктов, икры, шоколадных конфет',
        id: 3,
        addit_img: false
      },
        {text: 'Строительство дворца для турнира',
        id: 4,
        addit_img: false
      },
        {text: 'Размещение гаражей для гостевого автотранспорта',
        id: 5,
        addit_img: false
      },
        {text: 'Постройка сверхмощной радиостанции для передачи всему миру сенсационных результатов',
        id: 6,
        addit_img: false
      },
        {text: 'Создание аэропорта «Большие Васюки» с регулярным отправлением почтовых самолётов и дирижаблей во все концы света, включая Лос-Анжелос и Мельбурн',
        id: 7, 
        addit_img: true,
        addit_img_path: 'plane.png'
      }
      ],
      img_ids: [0, 1, 2, 3, 4]
    }
  },
  methods: {
    moveInfoRight () {
      this.infoCounter++;
    },
    moveInfoLeft () {
      this.infoCounter--;
    },
    changeState (value) {
      if (this.infoCounter === value) {
        return 'counter_dot-active.svg'
      } else {
        return 'counter_dot.svg'
      }
    }
  },
  computed: {
    btn_left_disabled () {
      return this.infoCounter === 0 ? true : false
    },
    btn_right_disabled () {
      return this.infoCounter === 4 ? true : false
    },
    btn_right_style () {
      return this.btn_right_disabled ? 'info_counter__right-disabled' : 'info_counter__right'
    },
    btn_left_style () {
      return this.btn_left_disabled ? 'info_counter__left-disabled' : 'info_counter__left'
    }
  }
}
</script>