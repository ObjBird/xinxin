<template>
  <div class="accessory-form">
    <div style="width:100%;height:20px;background-color:#f7f7f7"></div>
    <div class="form-item">
      <div>文件名</div>
      <div>上传人</div>
      <div>时间</div>
    </div>
    <div class="form-item">
      <div>身份证</div>
      <div>吴桐</div>
      <div>2020-01-01 10:00</div>
    </div>
    <div class="form-item">
      <div>工作证明</div>
      <div>吴桐</div>
      <div>2020-01-01 10:00</div>
    </div>
    <div class="form-item">
      <div>结婚证</div>
      <div>吴桐</div>
      <div>2020-01-01 10:00</div>
    </div>
  </div>
</template>

<script>
import accessoryJson from '../../accessory.json'; 
  export default {
    components: {
      
    },
    data(){
      return{
        accessoryJson:accessoryJson
      }
    },
    created:function(){
      // alert(JSON.stringify(this.accessoryJson))
      console.log(this.accessoryJson.data[0]);
    }
  }
</script>
<style scoped>
.form-item{
  display: flex;
  display: -webkit-flex;
  justify-content: center;
  align-items: center;
  height: 52px;
  width: 100%;
  border-bottom: 1px solid #BBBBBB;
  background-color: #FFFFFF;
}
.form-item div{
  font-size: 14px;
  width: 33.3%;
  text-align: center;
}
</style>

