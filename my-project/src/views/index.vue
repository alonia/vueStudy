<template lang="html">
  <!-- 在首页父组件发送http请求,后将数据通过props传递给子组件,可减少请求次数,减少服务器压力 -->
  <div class="index">
    <v-header></v-header>
    <v-swiper></v-swiper>
    <v-service></v-service>
    <v-section1 :section1="datas"></v-section1>
  </div>
</template>

<script>
import Header from '@/components/home/header.vue'
import Swiper from '@/components/home/swiper.vue'
import Service from '@/components/home/service.vue'
import Section1 from '@/components/home/section1.vue'
import axios from 'axios'
export default {
  components: {
    'v-header': Header,
    'v-swiper': Swiper,
    'v-service':Service,
    'v-section1':Section1
    },
    data() {
    return {
      datas: '',
      loading:true
    }
  },
   beforeCreate() {
     var that = this;
     axios.get('./static/dummy/image.json')
          .then(function (response) {
          that.datas = response.data.data;
          console.log(response.data.data);
          })
         .catch(function (error) {
           console.log(error);
          });
    
  }
}
</script>



<style lang="less" scoped>
.index {
    width: 100%;
    //padding-bottom: 14vw;
    background-color: #F8FCFF;
}
</style>
