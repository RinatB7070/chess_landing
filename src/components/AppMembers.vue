<template>
  <div class="members container">
    <h1 class="members__header">Участники турнира</h1>
    <div class="members__people">
      <div class="members__people__inner" :style="{'margin-left': '-' + onMobileMargin + 'px'}">
        <div 
          class="members__people__item" 
          v-for="member in members"
          :key="member.id"
          >
          <img src="../../public/assets/AppMembers/portrait.png" alt="portrait">
          <p class="members__people__item__name">{{ member.name }}</p>
          <p class="members__people__item__title">{{ member.title }}</p>
          <button>Подробнее</button>
        </div>
      </div>

    </div>
        <div class="members__buttons">
      <button
        :class="btn_left_style"
        @click="moveLeft"
        :disabled="btn_left_disabled"
        ></button>
      <p class="members__buttons__counter">{{ memberCounter + 1 }} / 6</p>
      <button
        :class="btn_right_style"
        @click="moveRight"
        :disabled="btn_right_disabled"
        ></button>
    </div>
  </div>
</template>

<script>
export default {
  props: ['isMobile'],
  data() {
    return {
      memberCounter: 0,
      members: [
        {
          name: 'Хозе-Рауль Капабланка',
          title: 'Чемпион мира по шахматам',
          id: 1
        },
        {
          name: 'Эммануил Ласкер',
          title: 'Чемпион мира по шахматам',
          id: 2
        },        {
          name: 'Александр Алехин',
          title: 'Чемпион мира по шахматам',
          id: 3
        },        {
          name: 'Арон Нимцович',
          title: 'Чемпион мира по шахматам',
          id: 4
        },        {
          name: 'Рихард Рети',
          title: 'Чемпион мира по шахматам',
          id: 5
        }
        ,        {
          name: 'Остап Бендер',
          title: 'Гроссмейстер',
          id: 6
        }
      ]
    }
  },
  methods: {
    moveLeft() {
      this.memberCounter--;
    },
    moveRight() {
      this.memberCounter++;
      console.log()
    }
  },
  computed: {
    btn_left_disabled () {
      return this.memberCounter === 0 ? true : false
    },
    btn_right_disabled () {
      return this.memberCounter === 5 ? true : false
    },
    btn_right_style () {
      return this.btn_right_disabled ? 'members__buttons__right-disabled' : 'members__buttons__right'
    },
    btn_left_style () {
      return this.btn_left_disabled ? 'members__buttons__left-disabled' : 'members__buttons__left'
    },
    onMobileMargin () {
      if (this.isMobile) {
        return (440 * (this.memberCounter))
      } else {
        return (340 * (this.memberCounter - 2))
      }
    }
  }
}
</script>