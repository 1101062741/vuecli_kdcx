<template>
  <div id="app">
    <Header></Header>
    <Input></Input>
    <Result></Result>
  </div>
</template>
<!-- 顺丰速运：465218695630 韵达：3915170594632 -->
<script>
import Header from './components/Header'
import Input from './components/Input'
import Result from './components/Result'
export default {
  name: 'App',
  components: {
    'Header': Header,
    'Input': Input,
    'Result': Result,
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 0.2rem;
}
</style>
