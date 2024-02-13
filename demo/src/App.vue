<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <ul>
      <li v-for="item in list" v-bind:key="item.title">{{item.title}}</li>
    </ul>
  </div>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'
import axios from 'axios'

export default {
  data(){
    return {
      list: {}
    }
  },
  name: 'App',
  components: {
    //HelloWorld
  },
  //(1) axios请求方式
  /*
  created(){
    axios({
      url: 'data.json'
    }).then(res => {  //数据请求成功会调用then()
      console.log(res);
      this.list = res.data;
    }).catch(err => {
      console.log(err);
    })     
  }
  */
  //(2) fetch请求方式一
  /*
  created(){
    var paramData = {"name": "laoni", "age": "40"};
    fetch('data.json', {
      method: 'post',
      headers: {
        //注意参数格式
        //'Content-Type': 'application/json',  //json数据格式
        'Content-Type': 'application/x-www-form-urlencoded',  //form数据格式
      },
      //body: JSON.stringify(paramData)
      body: 'name=laoni&age=40'
    });
  }*/
  //(3) fetch请求方式二
  /*created(){
    const result = fetch('data.json');
    console.log(result);   //promise对象
    result.then(res => {
      console.log(res);
    }).catch(err => {
      console.log(err);
    })
  }*/
  
  /*
   * text() 将数据解析成文本
    blob() 将数据解析为二进制对象, 比如上传
    json() 将数据解析为json格式字符串
   */
  //(4) ES7-async异步请求方式
  /*created(){
    var temp = this;
    async function getData(){
      try{
        const result = await fetch('data.json');
        const res = await result.json();
        console.log(res);
        temp.list = res;
      }catch(err){
        console.log(err);
      }      
    }
    getData();
  }*/
  //(5) 换一种写法async=> 箭头函数识别this
  created(){
    const getData = async() => {
      const res = await fetch('data.json');
      const result = await res.json();
      this.list= result;
    }
    getData();
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
