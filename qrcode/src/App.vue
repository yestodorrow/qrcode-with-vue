<template>
  <div id="app">
    <Hello></Hello>
    <Qrcode></Qrcode>
    <ul>
      <li v-for="item in ca">
        <span >{{item|get}}:</span>
        <span>{{item[1]}}</span>
      </li>
    </ul>
    <ul>
      <li v-for="item in lo" track-by="$index">
        <span>num{{$index}} ：</span>
        <span>{{item}}</span>
      </li>
    </ul>
  </div>
</template>

<script>

import Qrcode from './components/qrcode'
import Hello from './components/hello'
export default {
  name: 'App',
  data(){
    return{
      co:[],
     ca:[],
      lo:[]
  }
},
filter:{
  get:function(data){
    data=data.split("=");
    return data[0]+":"+data[1]
  }
},
  components: {
    Qrcode,Hello
  },
  mounted() {
    this.ca=document.cookie.split(";");
    for(var i=0;i<100;i++){
      if(!localStorage.getItem("num"+i)){
        return
      }else{
        this.lo.push(localStorage.getItem("num"+i))
      }
    }
  },

}

</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
