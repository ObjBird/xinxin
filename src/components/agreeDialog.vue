<template>
  <div class="popup">
    <div class="agree-dialog">
      <div class="opinion">
        <label>审批意见:</label>
        <textarea placeholder="请输入审批意见"></textarea>
      </div>
      <div class="assign">
        <label>人员</label>
        <select>
          <option style="width:20px;">王帅</option>
          <option>吴桐</option>
          <option>李超</option>
          <option>贝贝</option>
          <option>张龙</option>
        </select>
      </div>
      <input class="btn btn-submit" type="submit" value="确定" />
      <input class="btn btn-cancel" type="submit" value="取消" @click="cancel"/>
    </div>
  </div>
</template>

<script scoped>
export default {
  components: {

  },
  data() {
    return {
      show: false
      // node:{

      // },
      // person:{

      // }
    }
  },
  props: {

  },
  computed: {

  },
  methods: {
    cancel() {
      this.$emit("agreeShow", this.show);
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
  background-color: rgba(0, 0, 0, 0.5);
  display: flex;
  display: -webkit-flex;
  justify-content: center;
  align-items: flex-end;
}

.agree-dialog {
  width: 100%;
  display: flex;
  display: -webkit-flex;
  flex-direction: column;
  -ms-flex-direction: column;
  justify-content: flex-start;
  align-items: center;
  font-size: 14px;
  background-color: #FFFFFF;
}

.agree-dialog div {
  border-bottom: 1px solid #eee;
}

.opinion {
  width: 100%;
  text-align: center;
  font-size: 18px;
  height: 64px;
  display: flex;
  display: -webkit-flex;
  align-items: flex-start;
  justify-content: space-around;
  margin-top: 20px;
}

.opinion label {
  width: 30%;
  text-align: left;
  text-indent: 10px;
  font-size: 16px;
  margin-top: 2px;
}

.opinion textarea {
  width: 60%;
  height: 50px;
  border: 0;
  margin-right: 10px;
  font-size: 17px;
  outline: none;
  resize: none;
  color: inherit;
}

.assign {
  display: flex;
  display: -webkit-flex;
  align-items: center;
  justify-content: space-around;
  height: 54px;
  width: 100%;
  font-size: 17px;

}

.assign label {
  width: 30%;
  text-align: left;
  text-indent: 10px;
}

.assign select {
  width: 60%;
  height: 45px;
  border-radius: 5px;
  margin-right: 3px;
  text-indent: 5px;
  outline: none;
  margin-right: 10px;
  font-size: 17px;
  border: none;
}
.btn {
  width: 100%;
  height: 42px;
  margin-top: 10px;
  border: 1px solid #eee;
  font-size: 18px;
  border-radius: 4px;
}

.btn-submit {
  background-color: #5be3a5;
  color: #FFFFFF;
  margin-top: 40px;
  margin-bottom: 5px;
  border-color: transparent;
}

.btn-cancel {
  background-color: #f8f8f8;
}
</style>
