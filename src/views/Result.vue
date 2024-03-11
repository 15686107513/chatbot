<template>
  <div class="result">
   <Head/>
    <div class="result-content">
      <img src="../assets/result/back.png"/>
      <span class="result-doc">Doc title. docx</span>
      <div class="result-title">Search Results</div>
    </div>
    <Content/>
  </div>
  <div class="chat-panel">
    <div class="chat-title">AI Assistant</div>
    <a-tabs v-model:activeKey="activeKey" class="chat-tabs">
      <a-tab-pane key="1" tab="chat">
        <Chat/>
      </a-tab-pane>
      <a-tab-pane key="2" tab="filter">
        <Filter/>
      </a-tab-pane>
    </a-tabs>
  </div>
</template>
<script  lang="ts">
import Head from '../components/result/Head.vue';
import Content from '../components/result/Content.vue';
import Chat from '../components/result/Chat.vue';
import Filter from '../components/result/Filter.vue';
import { ref } from 'vue';

export default {
  components: {
    Head,
    Content,
    Chat,
    Filter
  },
  setup() {
    const activeKey = ref('1');
    return {
      activeKey
    };
  },

}
</script>

<style>
.ant-tabs-tab {
  font-size: 20px !important;
  font-weight: 500;
  color: #B2B6BC;
}
:where(.css-dev-only-do-not-override-1hsjdkk).ant-tabs .ant-tabs-tab.ant-tabs-tab-active .ant-tabs-tab-btn,
:where(.css-dev-only-do-not-override-1hsjdkk).ant-tabs .ant-tabs-tab-btn:focus:not(:focus-visible),
:where(.css-dev-only-do-not-override-1hsjdkk).ant-tabs .ant-tabs-tab-remove:focus:not(:focus-visible), 
:where(.css-dev-only-do-not-override-1hsjdkk).ant-tabs .ant-tabs-tab-btn:active,
:where(.css-dev-only-do-not-override-1hsjdkk).ant-tabs .ant-tabs-tab-remove:active,
:where(.css-dev-only-do-not-override-1hsjdkk).ant-tabs .ant-tabs-tab:hover {
  color: #000;
}
:where(.css-dev-only-do-not-override-1hsjdkk).ant-tabs .ant-tabs-ink-bar {
  background: #000;
}
.result {
  width: 70%;
  background-color: #F1F3FC;
  min-height: 100vh;
  .result-menu {
    width: 24px;
    height: 24px;
    margin: 0px 0 0 20px;
  }
  .result-doc {
    position: relative;
    bottom: 8px;
    left: 8px;
  }
  .result-content {
    padding: 20px 0 0 20px;
  }
  .result-search {
    width: 146px;
    height: 36px;
    background: #1D9BD1;
    color: #fff;
    border-radius: 6px;
    display: flex;
    justify-content: center;
    align-items: center;
    margin-right: 12px;
  }
  .result-list {
    width: 114px;
  }
  .result-plus {
    width: 16px;
    height: 16px;
  }
  .result-number {
    background-color: #fff;
    border-radius: 50%;
    width: 23px;
    height: 23px;
    color: #1D9BD1;
    display: flex;
    justify-content: center;
    align-items: center;
    margin-left: 8px;
  }
  .result-share {
    width: 28px;
    height: 28px;
  }
  .head-wrap {
    display: flex;
  }
  .result-title {
    font-size: 20px;
    font-weight: 600;
    margin-top: 10px;
  }
}
.chat-panel {
  width: 30%;
  padding: 10px 0 0 0px;
  background-image: linear-gradient(to bottom, #F1F3FC ,#fff);
  background-color: #F1F3FC;
  .chat-title {
    font-size: 20px;
    font-weight: 600;
  }
}
</style>
