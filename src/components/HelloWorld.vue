<!--
@Author: SimonSun <simon>
@Date:   08-03-2018 PM 17:03:54
@Email:  9262981@qq.com
@Project: FreeKeer.com
@Filename: HelloWorld.vue
@Last modified by:   simon
@Last modified time: 13-03-2018 PM 15:03:48
-->



<template>
  <div id="app">
    <p>{{ count }}</p>
    <a href="#/aaa">aaa</a>
    <p>
      <button @click="increment">+</button>
      <button @click="decrement">-</button>
    </p>
  </div>
</template>

<script>
import Vue from 'vue'
import Vuex from 'vuex'
Vue.use(Vuex)
const store = new Vuex.Store({
  state: {
    count: 0
  },
  mutations: {
  	increment: state => state.count++,
    decrement: state => state.count--
  }
})
export default {
  name: 'HelloWorld',
  computed: {
    count () {
      return store.state.count
    }
  },
  methods: {
    increment () {
      store.commit('increment')
    },
    decrement () {
      store.commit('decrement')
    }
  },
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  }
}
</script>
