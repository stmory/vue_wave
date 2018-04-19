<!--  -->
<template>
  <transition name="trans_wave">
    <div class="vueWave_cover" :style="thisStyle"></div>
  </transition>
</template>

<script>
export default {
  data () {
    return {
    };
  },
  props: {
    waveItemStyle: Object,
  },
  components: {
    
  },
  computed: {
    thisStyle() {
      return {
        width: this.waveItemStyle.width,
        height: this.waveItemStyle.height,
        top: this.waveItemStyle.top,
        left: this.waveItemStyle.left,
        'background-color': this.waveItemStyle.color,
      }
    },
  },
  methods: {
    setStyle() {

    },
  }
}

</script>
<style scoped>
.vueWave_main .vueWave_cover{
  position: absolute;
  border-radius: 50%;
  pointer-events: none;
  user-select: none;
  transition: all .5s;
  background-clip: padding-box;
  opacity: 0.1;
}
.trans_wave-enter-active, .trans_wave-leave-active{
  transition: opacity 2s cubic-bezier(0.23, 1, 0.32, 1), transform .45s cubic-bezier(0.23, 1, 0.32, 1);
}
.trans_wave-enter {
  transform: scale(0);
}
.trans_wave-leave-active{
  opacity: 0 !important;
}
</style>