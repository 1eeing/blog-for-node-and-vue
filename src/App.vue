<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <Test v-bind:msg="msg" v-bind:content="ptc" v-on:changeWithParent="change" />
    <span>父页面：{{msg}}</span>
  </div>
</template>

<script>
import Test from './components/test/index';

export default {
  name: 'app',
  data () {
    return {
      msg: '来自父页面',
      ptc: [
        {
          content: '我是来自父页面的数据1',
          id: 1
        },
        {
          content: '我是来自父页面的数据2',
          id: 2
        },
        {
          content: '我是来自父页面的数据3',
          id: 3
        }
      ]
    };
  },
  components: {
    Test
  },
  methods: {
    change(val) {
      this.msg = val;
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
