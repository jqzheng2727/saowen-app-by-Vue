<template>
  <div id="app">
    <myHeader></myHeader>
    <transition name="fade" mode="out-in"><router-view></router-view></transition>
    <!--尾部-->
    <div class="footer">
      <ul>
        <li><router-link to="/"><i class="iconfont icon-shouye2"></i><br>首页</router-link></li>
        <li><router-link to="/collectlist"><i class="iconfont icon-zhuanji"></i><br>书单</router-link></li>
        <li><router-link to="/search" ><i class="iconfont icon-more4"></i><br>扫文</router-link></li>
        <li><router-link to="/ranklist"><i class="iconfont icon-paixing1"></i><br>排行</router-link></li>
        <li><router-link to="/myhome"><i class="iconfont icon-wode1"></i><br>我的</router-link></li>
      </ul>
    </div>
    <myCover v-show="show"></myCover>
    <myLogin v-show="show"></myLogin>
  </div>
  </template>

<script>
import {mapState} from 'vuex'
import Header from './components/Header.vue'
import Cover from './components/Cover.vue'
import Login from './components/Login.vue'
export default {
  name: 'app',
  data(){
    return {
      show: false
    }
  },
  computed: {
    ...mapState([
      'islogin'
    ])
  },
  components: {
    myHeader: Header,
    myCover: Cover,
    myLogin: Login
  }
}
</script>

<style>
.fade-enter-active, .fade-leave-active {
    transition: all 0.3s;
}

.fade-enter, .fade-leave-active {
    opacity: 0.1;
}
</style>
