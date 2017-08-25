<template>
  <div>
    <div class="popup">
      <div class="more-dialog">
        <input class="first" type="submit" value="改派" />
        <input class="second" type="submit" value="委托" />
        <input type="submit" value="取消" @click="cancel"/>
    </div>
    </div>
  </div>
</template>

<script>
  export default {
    components: {
      
    },
    data(){
      return{
        show:false
      }
    },
    props: {
      
    },
    computed: {
     
    },
    methods: {
       cancel(){
        this.$emit("moreShow",this.show);
      }
    }
  }
</script>

<style scoped>
 .popup {
  position: absolute;
  left: 0px;
  bottom: 0px;
  top: 0px;
  right: 0px;
  background: rgba(255, 255, 255, 0.8);
  display: flex;
  display: -webkit-flex;
  flex-direction: column-reverse;
  justify-content: flex-start;
  align-items: center;
}

.more-dialog {
  width: 100%;
  display: flex;
  display: -webkit-flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: center;
  background-color: #FFFFFF;
  margin-bottom: 50px;
}
.more-dialog input:last-child{
  margin-top: 10px;
  border-radius: 5px;
  border: 1px solid #BBBBBB;
  font-weight: 600px;
}
.more-dialog div {
  width: 100%;
}

.more-dialog input {
  width: 80%;
  height: 45px;
  background-color: #FFFFFF;
  font-size: 19px;
}
.first{
  border-radius: 6px 6px 0 0;
  border: 1px solid #BBBBBB;
  border-bottom: none;
  color: #E51C23;
}
.second{
  border-radius: 0px 0px 6px 6px;
  border: 1px solid #BBBBBB;
  color: #555555;
}
</style>
