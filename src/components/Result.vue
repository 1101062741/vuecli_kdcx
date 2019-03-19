<template>
  <div class="result">
    <p class="title">查询结果：</p>
    <ol class="list">
      <li v-for="item in aresult"><span class="red">{{item.time}}</span>{{item.desc}}</li>
    </ol>
  </div>
</template>

<script>
import Bus from '../../static/js/Bus'
export default {
  name: 'Result',
  data () {
    return {
      aresult:null
    }
  },
  created(){
Bus.$on('getresultdata',value=>{
              this.add(value);
          });
  },
  beforeDestory(){//组件的钩子函数
            Bus.$off("getresultdata");
        },
        methods:{
          add(value){
                this.aresult=value;
                console.log(this.aresult)
            }
        }
  
}
</script>
*{margin:0;padding:0;}
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.result {
  width: 5.6rem;
  height: 4rem;
  border: 1px solid #ddd;
  margin: 0 auto;
  font-size: 0.28rem;
  text-align: left;
  padding: 0.1rem 0.2rem;
  border-radius: 0.1rem;
  background: #eee;
}
.title {
  color: blue;
}
.list{
  margin-top: 0.1rem;

}
.red{margin-right: 0.1rem;color: red;}
ol>li{line-height: 120%;}
</style>
