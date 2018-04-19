<!--  -->
<template>
  <wave class="box" color="#fff">
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
  width: 1000px;
  height: 100px;
}
</style>