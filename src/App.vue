<template>
  <div id="app" v-cloak>
    <header-common></header-common>
    <banner></banner>
    <service></service>
    <div class="midArea">
      <hot-case></hot-case>
      <news-and-understand-more></news-and-understand-more>
    </div>
    <below></below>
  </div>
</template>

<script>
import headerCommon from './components/common/headerCommon'
import banner from './components/index/banner'
import service from './components/index/service'
import hotCase from './components/index/hotCase'
import newsAndUnderstandMore from './components/index/newsAndUnderstandMore'
import below from './components/index/below'
export default {
  name: 'app',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
  components: {
    headerCommon,
    banner,
    service,
    hotCase,
    newsAndUnderstandMore,
    below
  }
}
</script>

<style lang="scss">
  @charset "utf-8";
  @import 'assets/scss/_mixin.scss';
  *, *:before, *:after{
    margin: 0;
    padding: 0;
    -moz-box-sizing: border-box;
    -webkit-box-sizing: border-box;
    box-sizing: border-box;
  }
  body, html{
    position: relative;
    background-color: #ffffff;
    width: 100%;
    height: 100%;
    font-family:"Microsoft JhengHei", "PMingLiU", "Arial Unicode MS", sans-serif;
    -webkit-overflow-scrolling: touch;
    -webkit-text-size-adjust: none;

    overflow-x: hidden;
  }
  #app {
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    // position: relative;
    // overflow: hidden;
    // background-color: #ccc;
  }

  .midArea{
    width: 1280px;
    background-color: #ffffff;
    overflow: hidden;
    margin: 0 auto;
    @include SCREEN_1300{
      width: 100%;
    }
  }
</style>

