<template>
  <div>
  <label @click="toggleSelect" for="select" class="">
    <p class="label-text">Тип контакта</p>
      <p class="label-content">{{chosenOption}}</p>
      <svg width="12" height="8" viewBox="0 0 12 8" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M1 1L5.83174 6L11 1" stroke="#818E94" stroke-width="2"/>
      </svg>
    </label>
  <select size="5" name="select" @change="onChooseOption(chosenOption)" v-model="chosenOption" :class="[!shown ? selectNone : selectBlock]">
    <option @click="toggleSelect" :key="index" v-for="(option, index) in fetchList" :value="option">
      {{option}}
    </option>
  </select>
  </div>
</template>

<script>

export default {
  name: 'HelloWorld',
  props: [
    'fetchList'
  ],
  data () {
    return {
      chosenOption: 'asd',
      shown: false,
      selectNone: 'select-none',
      selectBlock: 'select-block'
    }
  },
  methods: {
    onChooseOption (value) {
      this.$emit('onChooseOption', value)
    },
    toggleSelect () {
      this.shown = this.shown === true ? false : true
    }
  }
}

</script>

<style lang="scss" scoped>
select {
  width: 280px;
}
.select-none {
  display: none;
}
svg {
  position: relative;
  bottom: 51px;
  left: 89%;
}
.select-block {
  display: block;
}
.label-content {
  margin: 0;
  position: relative;
  bottom: 34px;
  left: 18px;
  font-family: Montserrat;
  font-style: normal;
  font-weight: normal;
  font-size: 16px;
}
label {
  display: block;
  background: #FFFFFF;
  border: 1px solid #C2CACD;
  box-sizing: border-box;
  border-radius: 6px;
  width: 280px;
  height: 40px;
}
.label-text {
font-family: Montserrat;
font-style: normal;
font-weight: 500;
font-size: 13px;
position: relative;
bottom: 27px;
left: 16px;
color:#727779;
}
label:hover{
  cursor: pointer;
}
</style>
