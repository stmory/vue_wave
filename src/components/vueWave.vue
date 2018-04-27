<!--  -->
<template>
  <div class="vueWave_main" :style="mainStyle">
    <div class="vueWave_slot" @click="startWave" ref="vueWave_slot">
      <slot name="content"></slot>
      <wave v-for="(item, index) in waveItemStyle" 
        :key="index" 
        :waveItemStyle="item">
      </wave>
    </div>
  </div>
</template>
<script>
import wave from './wave'

export default {
  data () {
    return {
      height: '',
      width: '',
      'border-radius': '',
      waveStyle: {
        height: '',
        width: '',
      },
      waveItemStyle: [],
    };
  },
  props: {
    color: String,
  },
  mounted() {
    this.setWidthAndHeight()
  },
  components: {
    wave,
  },
  computed: {
    mainStyle() {
      return {
        // height: this.height,
        // width: this.width,
        'border-radius': this['border-radius'],
      }
    },
  },
  methods: {
    setWidthAndHeight() {
      this.height = window.getComputedStyle(this.$slots.content[0].elm,null).height
      this.width = window.getComputedStyle(this.$slots.content[0].elm,null).width
      this['border-radius'] = window.getComputedStyle(this.$slots.content[0].elm,null)['border-radius']
    },
    startWave(event) {
      let box = this.getElBox(this.$refs.vueWave_slot)
      let waveX = event.offsetX
      let waveY = event.offsetY
      let pointTldis = this.sqrt(waveX, waveY)
      let pointTRdis = this.sqrt(box.width - waveX, waveY)
      let pointBLdis = this.sqrt(waveX, box.height - waveY)
      let pointBRdis = this.sqrt(box.width - waveX, box.height - waveY)
      let radius = Math.max(pointTldis, pointTRdis, pointBLdis, pointBRdis)
      let widthAndHeight = radius * 2
      let top = waveY - radius
      let left = waveX - radius
      this.waveItemStyle.push({
        width: widthAndHeight + 'px',
        height: widthAndHeight + 'px',
        top: top + 'px',
        left: left + 'px',
        color: this.color,
      }) 
      this.endWave()
    },
    endWave() {
      setTimeout(()=>{
        this.waveItemStyle.shift()
      }, 500)
    },
    getElBox(el) {
      let box = el.getBoundingClientRect()
      return {
        width: box.width,
        height: box.height,
      }
    },
    sqrt(a, b) {
      return Math.sqrt((a * a) + (b * b))
    }
  }
}

</script>
<style scoped>
.vueWave_main{
  position: relative;
  overflow: hidden;
}
.vueWave_slot{
  width: 100%;
  height: 100%;
  position: relative;
  overflow: hidden;
}
.div{
  position: absolute;
  left: 100px;
  top: 0;
}
</style>