<template>
  <div class="input">
    <select>
      <option value>-请选择-</option>
    </select>
    <input name="code" placeholder="请输入运单号">
    <button @click="get()">查询</button>
    <button @click="get2()">查询</button>
  </div>
</template>
<script>
export default {
  name: 'InputBox',
  data () {
    return {}
  },
  methods: {
    get () {
      this.axios.get('/static/json/company.json').then(
        function (res) {
          alert(JSON.stringify(res))
        },
        function () {
          alert('请求失败处理')
        }
      )
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
select,
input {
  margin: 0;
  padding: 0;
}
.input {
  display: flex;
  flex-direction: column;
  font-size: 0.28rem;
  justify-content: center;
  align-items: center;
}
input,
select {
  width: 5rem;
  font-size: 0.28rem;
  padding-left: 0.2rem;
  height: 0.4rem;
  line-height: 0.4rem;
  margin: 0.2rem 0;
}
select {
  width: 5.24rem;
  height: 0.5rem;
}
input {
  border: 1px solid #bbb;
  height: 0.46rem;
}
button {
  width: 2rem;
  background: none;
  border: none;
  background: lightblue;
  padding: 0.1rem 0.2rem;
  border-radius: 0.2rem;
  margin-top: 0.3rem;
  margin-bottom: 0.6rem;
}
option:first-child {
  color: #eee;
}
</style>
