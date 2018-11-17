<template>
  <div id="app">
    <Header id="header"></Header>
    <main id="main">
      <router-view/>
    </main>
    <Footer id="footer"></Footer>
  </div>
</template>

<script>
import Header from '@/components/header'
import Footer from '@/components/footer'

export default {
  name: 'App',
  components:{
    Header,
    Footer
  }
}
</script>

<style lang="less">
@import "./assets/common.less";

#app {
  display: grid;
  grid-template-columns:12% auto 12%;
  grid-template-rows:auto 1fr auto;
  grid-template-areas:"header header header"
                      ". main ."
                      "footer  footer  footer";
#header{
  grid-area:header;
  padding-left:12%;
  padding-right:12%;
}
#main{
  grid-area:main;
}
#footer{
  grid-area:footer;
  padding-left:12%;
  padding-right:12%;
}
  .el-button{
    font-size: 14px;
    height: 40px;
    line-height: 30px;
    padding: 0 20px;
    border-radius: 4px;
    font-weight: normal;
    color: rgb(204, 255, 217);
    background: rgb(15, 132, 47);
    border-color: #0c7928;
  }
  .el-button:hover,el-button:focus{
    color: #ccffd9;
    background: transparent;
    border-color: #afe6bd;
  }
}
@media(max-width:768px){
  #app{
    grid-template-columns:3% 94% 3%;
    grid-template-areas:"header header header"
                      ". main ."
                      "footer  footer  footer";
    #header,#footer{
      padding-left:0;
      padding-right:0;
    }
  }
}
</style>
