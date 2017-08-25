<template>
  <div class="container" id="main">
    <!-- <div class="top">
      <div class="btns">
        <span>< 返回</span>
        <span>关闭</span>
      </div>
      <h1>审批</h1>
    </div> -->
    <div class="middle">
      <div class="description">
        <span>立群</span>
        <em>杨立群的事项办理</em>
      </div>
      <strong><img src="\.\./\.\./static/agree.png" alt=""></strong>
    </div>
    <ul>
      <li>
        <v-link href="/">单据内容</v-link>
        <v-link href="/approvalHistory">审批历史</v-link>
        <v-link href="/accessory">附件</v-link>
      </li>
    </ul>

    <slot></slot>
  </div>
</template>

<script>
  import VLink from '../components/VLink.vue'

  export default {
    components: {
      VLink
    }
  }
</script>

<style scoped>
  .top{
    position: relative;
    border-bottom: 1px solid #ccc;
  }
  .middle{
    position: relative;
    height: 100px;
  }
  .middle .description{
    position: absolute;
    top:25px;
    left: 20px;
  }
  .description em{
    margin-left: 10px;
  }
  .middle span{
    display: inline-block;
    width: 50px;
    height: 50px;
    background: #04d087;
    color:#fff;
    border-radius: 50%;
    line-height: 50px;
    text-align: center;
  }
  .middle strong{
    position: absolute;
    right: 20px;
    top:10px;
   /* width: 80px;
    height: 80px;
    background: #04d087;
    color:#fff;
    border-radius: 50%;
    line-height: 80px;
    text-align: center;*/
    text-align: right;
  }
  .middle strong img{
    width: 40%;
  }
  #main .btns{
    position: absolute;
    left: 0px;
    top:  14px;
    font-size: 15px;
  }
  #main h1{
      font-weight: normal;
      font-size: 18px;
      text-align: center;
      height: 45px;
      width: 375px;
      line-height: 45px;
      margin: 0 auto;
    }
  #main.container {
    /*max-width: 375px;
    margin: 0 auto;*/
   /* padding: 15px 30px;
    background: #f9f7f5;*/
    /*position: relative;*/
  }
  #main li{
    list-style: none;
    display: flex;
    justify-content:space-around;
  }
 #main a{
    text-decoration: none;
    flex-grow:100; 
    font-size: 14px;
    height: 50px;
    line-height: 50px;
    text-align: center;
    cursor: pointer;
    color: black;
    border-top: 1px solid #eee;
    font-weight: bold;
  }
</style>
