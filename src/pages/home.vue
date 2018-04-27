<!--  -->
<template>
  <div>
    <div class="demo">
    <!-- 用于普通div -->
      <wave class="box" color="#ffffff">
        <div class="item" slot="content">
        圆形
        </div>
      </wave>
      <wave class="box" color="#ffffff">
        <div class="item2" slot="content">
        矩形
        </div>
      </wave>
      <wave class="box" color="#ffffff">
        <div class="item3" slot="content">
        圆角矩形
        </div>
      </wave>
      <wave class="box" color="#ffffff">
        <div class="item4" slot="content">
        用于普通块级元素
        </div>
      </wave>
    </div>
    <div class="demo">
    <!-- 用于组件 -->
      <wave class="box" color="#ffffff">
        <but slot="content"
        text='用于组件'></but>
      </wave>
      <wave class="box" color="#2b85e4">
        <div class="item3" style="background-color: #fff;color:#222" slot="content">
          不一样的
        </div>
      </wave>
      <wave class="box" color="#ed3f14">
        <div class="item3" style="background-color: #fff;color:#222" slot="content">
          点击颜色
        </div>
      </wave>
    </div>
  </div>
</template>

<script>
import wave from '../components/vueWave'
import but from './button'

export default {
  data () {
    return {
    };
  },

  components: {
    wave,
    but,
  },

  computed: {},

  methods: {}
}
</script>
<style scoped>
.box{
  margin: 30px;
}
.demo{
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  font-size: 12px;
}
.item{
  background-color: #19be6b;
  border-radius: 50%;
  color: #fff;
  line-height: 50PX;
  text-align: center;
  width: 50px;
  height: 50px;
}
.item2{
  background-color: #ff9900;
  color: #fff;
  line-height: 50PX;
  text-align: center;
  width: 100px;
  height: 50px;
}
.item3{
  background-color: #ed3f14;
  border-radius: 10px;
  color: #fff;
  line-height: 50PX;
  text-align: center;
  width: 100px;
  height: 50px;
}
.item4{
  background-color: #2d8cf0;
  border-radius: 10px;
  color: #fff;
  line-height: 50PX;
  text-align: center;
  width: 150px;
  height: 50px;
}
</style>