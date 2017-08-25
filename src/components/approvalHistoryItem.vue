<template>
  <div class="approve-content">
    <div class="content-left"></div>
    <div class="content-right">
      <div class="upLoading" v-show=upLoadShow >
          下拉刷新
      </div>
      <div class="content-item" v-for="message in approvalHistoryJson.data" :key="message.id">
        <div class="arrow">
          <div class="arrow-right"><i class="iconfont">&#xe66a;</i></div>
          <div class="arrow-left"></div>
        </div>
        <div class="item-content">
          <div class="item-content-img">
            <div class="imgName">
              {{message.name}}
            </div>
          </div>
          <div class="item-content-message">
            <div class="message">
              <h2>{{message.name}}</h2>
              <p>{{message.currentDate}}</p>
            </div>
            <div class="message">
              <p class="message-opinion">{{message.approvalOpinion}}</p>
              <p><i class="iconfont">&#58987;</i></p>
            </div>
          </div>
        </div>
      </div>
      <div style="height: 20px;"></div>
      <div class="loading" v-show=loadShow >
          正在加载...
      </div>
    </div>
  </div>
</template>

<script>
import approvalHistoryJson from '../../approvalHistory.json';
export default {
  components: {
  },
  data() {
    return {
      approvalHistoryJson: approvalHistoryJson,
      isRefresh: false,
      isLoadingMore: false,
      loadShow:false,
      upLoadShow:false
    }
  },
  created: function() {
  },
  mounted() {
    //在vue实例上，临时增加一个属性scrollFoods，不需要实现数据绑定，不用在data中设置
    this.scrolls = new IScroll(".approvalContent",{
      click : true,
      probeType: 2
    });
    //在scrollFoods上注册事件
    //子级高度
    var listHeight = document.querySelector('.approve-content').clientHeight;
    // 父级高度
    var containerHeight = document.querySelector('.approvalContent').clientHeight;
    var freshheight = -50;
    this.scrolls.on('scroll',() => {
      // console.log(this.scrolls.y);
      if(this.scrolls.y > 10 && this.isRefresh === false) {
          this.upLoadShow=true;
      }
      if(this.scrolls.y > 50 && this.isRefresh === false){
          this.isRefresh = true
          document.querySelector('.upLoading').innerHtml="正在刷新...";
          console.log(document.querySelector('.upLoading'));
          console.log(document.querySelector('.upLoading').innerHtml);
          setTimeout(() => {
            console.log('下拉刷新');
            this.isRefresh = false;
            this.upLoadShow=false;
          },1500);
      }
      if( containerHeight + freshheight - this.scrolls.y >= listHeight && this.isLoadingMore === false) {
        console.log('load more....');
        this.loadShow=true;
        this.isLoadingMore = true;
        setTimeout(() => {
          console.log('load done');
          this.isLoadingMore = false; 
          this.loadShow=false;
        },1500);
      }
    });
  }
}
</script>
<style scoped>
.loading{
  position: absolute;
  left: 0px;
  bottom:-28px;
  height: 50px;
  width: 100%;
  text-align: center;
}
.upLoading{
  margin-top: 20px;
  text-align: center;
}
.approve-content {
  background-color: #f7f7f7;
  display: flex;
  display: -webkit-flex;
  justify-content: flex-start;
  font-size: 14px;
}

.content-left {
  width: 5%;
  border: none;
  border-right: 1px solid #BBBBBB;
  min-height: 508px;
}

.content-right {
  height: 100%;
  margin-left: 20px;
  width: 95%;
}

.content-item {
  margin-right: 7%;
  margin-top: 10px;
  height: 120px;
  display: flex;
  display: -webkit-flex;
  justify-content: center;
  align-items: center;
}
.arrow{
  margin-left: -38px;
  display: flex;
  display: -webkit-flex;
  justify-content: flex-start;
  align-items: center;
}
.arrow-right{
  width: 22px;
  height: 22px;
  border-radius: 50%;
  color: #FFFFFF;
  background-color: #63F680;
  line-height: 24px;
  text-indent: 3px;
}
.arrow-left{
  border-width: 8px;
  border-style: solid;
  border-color: transparent;
  border-right-color: #FFFFFF;
}
.item-content {
  display: flex;
  display: -webkit-flex;
  justify-content: flex-start;
  height: 96px;
  width: 95%;
  background-color: #FFFFFF;
  border-radius: 5px;
  align-items: center;
}

.item-content-img {
  width: 70px;
  height: 70px;
  margin-left: 10px;
  display: flex;
  display: -webkit-flex;
  justify-content: center;
  align-items: center;
}

.imgName {
  padding: 5px;
  width: 40px;
  height: 40px;
  border-radius: 50%;
  background-color: #63BEF6;
  line-height: 40px;
  font-size: 17px;
  color: #FFFFFF;
  text-indent: 3px;
}

.item-content-message {
  margin-left: 10px;
  display: flex;
  display: -webkit-flex;
  flex-direction: column;
  -ms-flex-direction: column;
  justify-content: flex-start;
  width: 90%;
  margin-right: 20px;
}
.message{
  display:flex;
  display: -webkit-flex;
  justify-content: space-between;
  align-items: center;
}
.item-content-message h2 {
  font-size: 16px;
}

.item-content-message p {
  font-size: 12px;
  line-height: 24px;
  color: #666666;
}
.message-opinion{
  width: 90%;
}
</style>
