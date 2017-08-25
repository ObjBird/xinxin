<template>
  <main-layout>
    <div class="approvalContent">
      <approval-history></approval-history>
    </div>
    <!-- <div class="refreshTop">111</div> -->
    <!-- <div class="refreshBottom">正在加载...</div> -->
  </main-layout>
</template>

<script>
  import MainLayout from '../layouts/Main.vue';
  import ApprovalHistory from '../components/approvalHistoryItem.vue';

  export default {
    data() {
      return {
        isRefresh: false,
        isLoadingMore: false
      }
    },
    components: {
      MainLayout,
      ApprovalHistory
    }
  }
  
</script>
<style>
  .approvalContent{
    position: absolute;
    left : 0;
    right: 0;
    top: 153px;
    bottom:0px;
    overflow: hidden;
    background: #f7f7f7;
  }
  .refreshBottom{
    position: fixed;
    left: 0px;
    bottom: 0px;
  }
</style>
