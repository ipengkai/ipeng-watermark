<template>
<div class="test-box">
  <div @click="tabTest">test</div>
</div>
  <IpengWatermark el="body" txt="测试"/>
</template>

<script>
import IpengWatermark from './components/IpengWatermark.vue'

export default {
  name: 'App',
  components: {
    IpengWatermark
  },
  methods:{
    tabTest(){
      console.log('tabTest')
    }
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  background:#f2f2f2;
}
.test-box{
  position: relative;
  // width: 500px;
  // height: 500px;
  background: #ffffff;
}
</style>
