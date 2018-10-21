<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <Test v-bind:msg="msg" v-bind:content="ptc" v-on:changeWithParent="changeWithParent"/>
    <span>{{msg}}</span>
  </div>
</template>

<script>
// @ is an alias to /src
import Test from '../components/test'

export default {
  name: 'home',
  data() {
    return {
      msg: '来自父页面',
      ptc: [
        {
          content: '列表1',
          id: 1
        },
        {
          content: '列表2',
          id: 2
        },
        {
          content: '列表3',
          id: 3
        },
      ]
    }
  },
  methods: {
    changeWithParent(val) {
      this.msg = val;
    }
  },
  components: {
    Test
  }
}
</script>
