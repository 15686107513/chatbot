<template>
  <div class="detail">
    <Head/>
    <div class="detail-content">
      <img src="../assets/result/back.png"/>
      <span class="detail-back">Back to results</span>
      <div class="detail-title">Complete faster than estimation with quality.Or think through and give more.</div>
      <div class="detail-avator">
        <img src="../assets/result/country.png" class="content-img"/>
        <span>US</span>
        <div class="active">Active</div>
      </div>

      <div class="detail-public">
        <div class="detail-block">
          <div class="detail-date">2016-11-15</div>
          <div class="detail-info">Publication date</div>
        </div>
        <div class="detail-block">
          <div class="detail-date">2015-06-21</div>
          <div class="detail-info">Application date</div>
        </div>
        <div class="detail-block">
          <div class="detail-date">2016-11-15</div>
          <div class="detail-info">Application Number</div>
        </div>

        <div class="detail-block">
          <div class="detail-date">NXP USA</div>
          <div class="detail-info">Assistant</div>
        </div>
        <div class="detail-block">
          <div class="detail-date">US</div>
          <div class="detail-info">Country</div>
        </div>
        <div class="detail-interactive">
          <img src="../assets/detail/add.png" class="detail-add"/>
          <img src="../assets/detail/download.png" class="detail-download"/>
        </div>
      </div>
      <div class="detail-smart">
        <span class="detail-smart-title">Smart Summary</span>
        <div class="detail-smart-info">Complete faster than estimation with hight quality. Or think through and give more suggestion to Product or Client, and could, complete faster than estimation with hight quality. Or think through and give more suggestion to Product or Client, and could...</div>
      </div>
      <div class="detail-line"></div>
      <div class="detail-abstract">

        <div class="detail-abstract-title">
          <div class="detail-sign"></div>
          <span>Abstract</span>
        </div>
        <div class="detail-abstract-info">Complete faster than estimation with hight quality. Or think through and give more suggestion to Product or Client, and could...</div>
      </div>
    </div>

  </div>
  <div class="chat-panel">
    <div class="chat-title">AI Assistant</div>
    <Chat :isShowSelect="false"/>
  </div>
</template>
<script lang="ts">
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
.detail {
  width: 70%;
  background-color: #F1F3FC;
  min-height: 100vh;
  .detail-avator {
    display: flex;
    margin-top: 10px;
    span {
      color: #6149F8;
    }
  }
  .active {
    margin-left: 34px;
    color: #3CCEA2;
    background-color: #E2F9F3;
    border: 1px solid #3CCEA2;
    padding: 1px 4px;
    border-radius: 8px;
    font-size: 12px;
  }
  .detail-public {
    display: flex;
    font-size: 14px;
    margin-top: 24px;
    position: relative;
  }
  .detail-date {
    color: #171923;
  }
  .detail-info {
    color: #9DA1B3;
    margin-top: 4px;
  }
  .detail-block {
    margin-right: 32px;
  }
  .detail-interactive {
    position: absolute;
    bottom: 0px;
    right: 0px;
  }
  .detail-add {
    width: 24px;
    height: 24px;
    margin-right: 14px;
  }
  .detail-download {
    width: 24px;
    height: 24px;
  }
  .detail-back {
    position: relative;
    bottom: 8px;
    left: 8px;
  }
  .detail-content {
    padding: 20px 20px 0 20px;
  }
  .detail-title {
    font-size: 20px;
    font-weight: 600;
    margin-top: 10px;
  }
  .detail-line {
    border-bottom: 1px solid #E9EBF1;
    padding-top: 32px;
  }
  .detail-sign {
    width: 5px;
    height: 16px;
    margin-right: 3px;
    background-color: #6149F8;
  }
  .detail-abstract-title {
    color: #171923;
    font-size: 16px;
    display: flex;
    align-items: center;
  }
  .detail-abstract-info {
    font-size: 14px;
    color: #6F7387;
    margin-top: 12px;
    line-height: 20px;
  }
  .content-img {
    width: 22px;
    height: 22px;
    margin-right: 10px;
  }
  .detail-smart {
    color: #6F7387;
    padding: 12px 20px;
    background-color: #F0EDFF;
    border-radius: 5px;
    margin-top: 25px;
  }
  .detail-smart-title {
    color: #6149F8;
    font-size: 16px;
    margin-bottom: 8px;
  }

  .detail-smart-info {
    font-size: 14px;
  }
}
.chat-panel {
  position: relative;
  width: 30%;
  min-width: 360px;
  padding: 10px 0 0 0px;
  background-image: linear-gradient(to bottom, #F1F3FC ,#fff);
  background-color: #F1F3FC;
  .chat-title {
    font-size: 20px;
    font-weight: 600;
    border-bottom: 1px solid #E9EBF1;
    padding-bottom: 15px;
  }
}
</style>
