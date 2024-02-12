<template>
  <div id="app" class="warp">
    <!--
    <img alt="Vue logo" src="./assets/logo.png">
     <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <box v-for="item in list" v-bind:key="item.title" v-bind:boxes="item"></box>
  </div>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'
import Box from './components/Box.vue'
import "./assets/reset.css"

export default {
  name: 'App',
  components: {
    Box
  },
  data(){
    return {
      list: {},
      numTitle: [
        ['阅读', '热度'],
        ['回答', '点赞'],
        ['回答', '采纳'],
      ]
    }
  },
  created(){
    const returnData = async() => {
      const res = await fetch('data.json');
      const result = await res.json();

      //处理数据, 给数据添加新的内容
      result.map((section, i) => {
        section.data.map(item => {
          item['read-num'] = item['read-num'] + this.numTitle[i][0];
          item['thumb-num'] = item['thumb-num'] + this.numTitle[i][1];
        })
      });

      this.list = result;
    }
    returnData();
  }
}
</script>

<style scoped>  
  .warp{
    display: flex;
  }
</style>
