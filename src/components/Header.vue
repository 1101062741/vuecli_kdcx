<template>
  <div class="header">{{msg}}</div>
</template>
<script>
export default {
  name: 'Header',
  data () {
    return {
      msg: '快递查询系统'
    }
  }
}
</script>
<style scoped>
.header {
  font-size: 0.28rem;
  text-align: center;
  color: #000;
  margin-bottom: 0.4rem;
}
</style>
