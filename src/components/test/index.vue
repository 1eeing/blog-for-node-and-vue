<template>
    <div>
        <div>
            <label>组件内通信：</label>
            <input type="text" v-on:keyup="changeOnlyMe" />
            <span>{{myself}}</span>
        </div>
        <div>
            <label>父子组件互通：</label>
            <input type="text" v-on:keyup="changeWithParent" />
            <span>{{msg}}</span>
        </div>
        <div>
            <label>父组件传递给子组件，子组件单独维护：</label>
            <input type="text" v-on:keyup="changeFromParent" />
            <span>{{message}}</span>
        </div>
        <!-- 循环 -->
        <ul>
            <li v-for="item in content" v-bind:key="item.id">
                {{item.content}}
            </li>
        </ul>
    </div>
</template>

<script>
// 单页面通信
export default {
  name: 'test',
  props: ['msg', 'content'],
  data() {
      return {
          myself: '我自己的消息',
          message: this.msg
      };
  },
  methods: {
      //组件内通信
      'changeOnlyMe': function(e) {
          this.myself = e.target.value;
      },
      //子组件跟父组件通信
      'changeWithParent': function(e) {
          this.$emit('changeWithParent', e.target.value);
      },
      //父组件将数据传递进来，子组件单独维护
      'changeFromParent': function(e) {
          this.message = e.target.value;
      }
  }
}
</script>
