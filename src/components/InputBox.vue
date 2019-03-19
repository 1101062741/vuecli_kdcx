<template>
  <div class="input">
    <select v-on:change="indexSelect($event)">
      <option value>-请选择-</option>
      <option
        v-for="item in company"
        v-bind:value="item.code"
        v-bind:key="item.code"
      >{{ item.name }}</option>
    </select>
    <input name="code" placeholder="请输入运单号" v-model="inputno">
    <button v-on:click="submit">查询</button>
  </div>
</template>
<script>
import Bus from '../../static/js/Bus'
export default {
  name: 'InputBox',
  data () {
    return {
      tool: 'haha',
      company: null,
      chooseCompany:null,
      inputno:null,
      result:null
    }
  },
  mounted: function () {
    this.get()
  },
  methods: {
    get () {
      this.axios.get('/static/json/company.json').then(
        res => {
          this.company = res.data
        },
        () => {
          alert('请求失败处理')
        }
      )
    },
    indexSelect(event){

　　console.log(event.target.value);
    this.chooseCompany=event.target.value

},
submit(){
  if(this.chooseCompany=="sf"&&this.inputno=="123"){
    console.log('submit');
    this.axios.get('/static/json/result.json').then(
      res =>{
        this.result=res.data;
        console.log(res.data);
        Bus.$emit('getresultdata',res.data);
      },
      ()=>{
        alert('请求失败处理')
      }
    )
  }
},
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
