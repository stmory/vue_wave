<!--  -->
<template>
  <wave class="box" color="#000">
    <div class="item" slot="content">
      111
    </div>
  </wave>
</template>

<script>
import wave from '../components/vueWave'

export default {
  data () {
    return {
    };
  },

  components: {
    wave,
  },

  computed: {},

  methods: {}
}
</script>
<style scoped>
.box{
  margin: 30px;
}
.item{
  background-color: rgb(91, 137, 223);
  border-radius: 50%;
  line-height: 100PX;
  text-align: center;
  width: 100px;
  height: 100px;
}
</style>