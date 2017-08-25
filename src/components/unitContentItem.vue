<template>
<div class="UnitContent">
  <div id="unitContent">
     <p v-for="item in unitContentJson.data">
      <span>{{item.name}}:</span>
      <em>{{item.value}}</em>
    </p>
  </div>
  <div class="unitBottom">
      <ul>
        <li @click="agree">同意</li>
        <li @click="reject">驳回</li>
        <li @click="more">改派</li>
        <li @click="more">委托</li>
      </ul>
  </div>
  <agree-dialog v-show=showAgreeDialog @agreeShow="changeAgree"></agree-dialog>
  <reject-dialog v-show=showRejectDialog @rejectShow="changeReject"></reject-dialog>
  <more-dialog v-show=showMoreDialog @moreShow="changeMore"></more-dialog>
</div>
</template>

<script>
  import AgreeDialog from '../components/agreeDialog.vue';
  import RejectDialog from '../components/rejectDialog.vue';
  import MoreDialog from '../components/moreDialog.vue';
  import unitContentJson from '../../unitContent.json';
  export default {
    components: {
      AgreeDialog,
      RejectDialog,
      MoreDialog
    },
    data(){
      return{
        showAgreeDialog:false,
        showRejectDialog:false,
        showMoreDialog:false,
        unitContentJson:unitContentJson
      }
    },
    props: {
      
    },
    computed: {
     
    },
    methods: {
      agree() {
        this.showAgreeDialog=true;
      },
      reject() {
         this.showRejectDialog=true
      },
      more() {
         // this.showMoreDialog=true
      },
      changeAgree(e){
        this.showAgreeDialog=e;
      },
      changeReject(e){
        this.showRejectDialog=e;
      },
      changeMore(e){
        this.showMoreDialog=e;
      }
    }
  }
</script>

<style scoped>
  .UnitContent{
    background: #f7f7f7;
   /* position: absolute;
    left : 0;
    right: 0;
    top: 154px;
    bottom:47px;*/
    border-top: 1px solid transparent;
  }
  #unitContent{
    /*padding:20px 60px 40px 30px;*/
    padding: 20px 0px 0px 30px;
    margin-top: 15px;
    background: #fff;   
  }
  #unitContent p{
     margin-bottom: 20px;
     border-bottom: 1px solid #f6f6f6;
  }
  #unitContent p span{
    display: inline-block;
    width: 37%;
    text-align: left;
    font-size: 14px;
    height: 25px;
    color: #bababa;
  }
  #unitContent p em{
    width: 60%;
    height: 25px;
    color: #555555;
    font-size: 14px;
  }
  .unitBottom{
    position: fixed;
    left: 0px;
    bottom: 0px;
    width: 100%;
  }
  .unitBottom ul{
    display: flex;
    justify-content:space-around;
  }
  .unitBottom ul li{
     flex-grow:100; 
     text-align: center;
     height: 45px;
     cursor: pointer;
     line-height: 45px;
     border:1px solid transparent;
     background: #f9f9f9;
     color: #fff;
  }
  .unitBottom ul li:nth-of-type(1){
    background: #5be3a5;
  }
  .unitBottom ul li:nth-of-type(2){
    background: #eb596c;
  }
  .unitBottom ul li:nth-of-type(3){
    background: #60cbf7;
  }
  .unitBottom ul li:nth-of-type(4){
    background: #2a70ac;
  }
</style>
