<template>
  <div class="popup">
    <div class="reject-dialog">
      <div class="opinion">
        <label>审批意见:</label>
        <textarea placeholder="请输入审批意见"></textarea>
      </div>
      <div class="assign">
        <label>驳回至</label>
        <select>
          <option>节点</option>
          <option>人员</option>
        </select>
      </div>
      <div class="assign">
        <label>节点</label>
        <select>
          <option>节点1</option>
          <option>节点2</option>
          <option>节点3</option>
          <option>节点4</option>
          <option>节点5</option>
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
    }
  },
  props: {

  },
  computed: {

  },
  methods: {
    cancel() {
      this.$emit("rejectShow", this.show);
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

.reject-dialog {
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

.reject-dialog div {
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
  margin-top: 3px;
}

.opinion textarea {
  width: 60%;
  height: 50px;
  border: 0;
  margin-right: 10px;
  font-size: 16px;
  outline: 0;
  resize: none;
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
 /* padding-left: 10px;*/
 /* appearance:none;
 -moz-appearance:none;
 -webkit-appearance:none;
 background: url("static/arrow.png") no-repeat scroll right center transparent;*/
}
/*.assign select::-ms-expand { display: none; }*/





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
  border-color: transparent;
  margin-top: 40px;
  margin-bottom: 5px;
}

.btn-cancel {
  background-color: #F8F8F8;
}
</style>
