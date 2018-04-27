<!--  -->
<template>
  <div class="btn">
    {{text}}
  </div>
</template>

<script>
export default {
  data () {
    return {
    
    };
  },
  props: {
    text: '',
  }
}

</script>
<style scoped>
.btn{
  padding: 10px 20px;
  border-radius: 8px;
  color: #fff;
  background-color: #2d8cf0;
  font-size: 12px;
  cursor: pointer;
  transition: all .3s;
}
.btn:hover{
  background-color: #5cadff;
}
</style>