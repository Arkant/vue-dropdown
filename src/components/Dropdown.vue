<template>
<div class="mdc-select mdc-select--outlined">
  <i class="mdc-select__dropdown-icon"></i>
  <select class="mdc-select__native-control">
    <option value="" disabled selected></option>
    <optgroup>
    <option :key="index" v-for="(option, index) in fetchList" :value="option">
      {{option}}
    </option>
    </optgroup>
  </select>
  <label class="mdc-floating-label mdc-floating-label--float-above">Тип контакта</label>
  <div class="mdc-line-ripple"></div>
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
    }
  }
}

</script>

<style lang="scss" scoped>
@import "@material/select/mdc-select.scss";
.mdc-select {
  background-color: white !important;
  border: 1px solid #E5E5E5;
  border-radius: 6px;
  width: 280px;
  height: 40px;
}
.mdc-select__native-control {
  padding-top: 0px !important;
}

option {
  background-color:#F5F6FA;
  // overflow: auto;
}
.mdc-select__dropdown-icon {
  bottom: 7px;
}
</style>
