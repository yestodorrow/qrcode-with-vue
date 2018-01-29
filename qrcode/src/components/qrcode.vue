<template>
  <div class="code">
    <input type="text" v-model="www"/>
    <button @click="generateQrcode">生成二维码</button>
    <div class="qr"></div>
  </div>
</template>
<script>

  export default{
  name:"what",
  data(){
   return {
     www:"http://www.baidu.com",
     num:0
   }
},
  methods:{
    generateQrcode(){
      $(".qr").html("").qrcode({
        render:"canvas",
        width:100,
        height:100,
        text:this.www,
        correctLevel:2,
        foreground:"#000000"
      })
      localStorage.setItem("num"+this.num++,this.www)
    }
}
}
</script>
<style scoped>
  .code{
    margin:10px;
    padding:10px;
    background:#ddd;
  }
  .qr{
    position:relative;
    width:100px;
    height:100px;
    margin:10px;
    border:5px solid #fff;
    top:50%;
    left:50%;
    transform:translate(-50%,0%)
  }
</style>
