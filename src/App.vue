<template>
  <div id="app">
    <Dropdown @onChooseOption="setOption($event)" :fetchList="fetchList"></Dropdown>
      Выбран:
    {{
      selectedOption
    }}
    <router-view/>
  </div>
</template>

<script>
import Dropdown from '@/components/Dropdown'
import {data} from './mocks/contacts.mock'
import axios from 'axios'

export default {
  name: 'App',
  components: {
    Dropdown
  },
  data () {
    return {
      fetchList: [],
      selectedOption: ''
    }
  },
  methods: {
    setOption (value) {
      this.selectedOption = value
    }
  },
  created () {
    // emit query
    axios.get('', {}).then((res) => {
      res = data
      this.fetchList = res
    })
  }
}
</script>

<style>
</style>
