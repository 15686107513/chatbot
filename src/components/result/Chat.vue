<template>
  <div class="chat">
    <template v-for="(message, index) in messages" :key="index">
      <div class="chat-content"  v-if="message.role==='user'">
        <img src="../../assets/result/avatar.png" class="chat-img"/>
        <div class="detail ai-detail">{{ message.content }}</div>
      </div>
      <div class="chat-content" v-if="loading && index === messages.length - 1">
        <img src="../../assets/result/AI.png" class="chat-img"/>
        <div class="detail ai-detail">Generating answer...</div>
      </div>
      <div class="chat-content" v-else-if="message.role==='assistant'">
        <img src="../../assets/result/AI.png" class="chat-img"/>
        <div class="detail">{{ message.content }}</div>
      </div>
    </template>

    <div class="chat-textarea">
        <div v-if="isShowSelect" class="chat-selected">Selected <span class="chat-selected-word">High quality or think through give  ...</span></div>
        <a-textarea
            v-model:value="textVal"
            placeholder="Tell me what you want to do with the selected content"
            :auto-size="{ minRows: 4, maxRows: 6 }"
            @pressEnter.prevent="pressEnter"
        />
        <div class="chat-prompt">
            <div class="chat-word">Please amend</div>
            <div class="chat-word">Rewrite</div>
            <div class="chat-word">Improve</div>
            <img src="../../assets/result/share.png" class="chat-share-img"/>
        </div>
    </div>
  </div>
</template>
<script>
import { CHAT_URL }  from '../../assets/const';
import axios from 'axios';
import { ref } from 'vue';
export default {
  data() {
    return {
      messages: [],
      loading: false,
      intervalId: null,
      thread: '',
      prompt: ''
    }
  },
  props:  {
    isShowSelect: {
      default: true,
    }
  },
  setup() {
    const textVal = ref('');
    return {
      textVal
    };
  },
  methods: {
    pressEnter(val) {
        this.textVal = '';
        this.prompt = val;
        this.messages.push({content: val, role: 'user'});
        this.addMessage();
        window.scrollTo(0, document.body.scrollHeight);
        this.loading = true;
    },
    addMessage() {
      axios({
        method: 'post',
        url: CHAT_URL,
        headers: {
          'Content-Type': 'application/json',
        },
        data: {
          thread: this.thread,
          prompt: this.prompt
        }
      }).then(res => {
        if (res.data) {
          this.loading = false;
          this.thread = res.data.thread;
          this.messages.push({content: res.data.response, role: 'assistant'});
        }
      }).catch(err => {
          console.log(err);
      });
    }
  }
}
</script>
<style>
.textarea {
  position: fixed;
  bottom: 60px;
  width: 100%;
}

  :where(.css-dev-only-do-not-override-1hsjdkk).ant-input:focus,
  :where(.css-dev-only-do-not-override-1hsjdkk).ant-input:hover,
  :where(.css-dev-only-do-not-override-1hsjdkk).ant-input-focused {
      border-color: #B2E2F9;
      box-shadow: 0 0 0 1px #B2E2F9;
  }
  .chat {
    width: 100%;
    :where(.css-dev-only-do-not-override-1hsjdkk).ant-input {
      border-color: #B2E2F9;
      border-radius: 18px 18px 0 0;
  }
  .chat-textarea {
    position: absolute;
    width: 92%;
    bottom: 20px;
    right: 4%;
  }
  .chat-content {
    display: flex;
    margin-top: 20px;
    max-width: 70%;
    word-break: break-word;
  }
  .chat-prompt {
    position: relative;
    display: flex;
    align-items: center;
    background-color: #B2E2F9;
    height: 50px;
    border-radius: 0 0 18px 18px;
  }
  .chat-selected {
    color: #171923;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
    font-weight: 700;
    font-size: 16px;
    border-radius: 50px;
    background-color: #EDF2FA;
    padding: 5px 10px;
    margin-bottom: 10px;
  }
  .chat-selected-word {
    color: #000;
  }
  .chat-word {
    color: #0A5171;
    background-color: #EBF9FF;
    padding: 6px 8px;
    line-height: 20px;
    margin-left: 10px;
    border-radius: 50px;
  }
  .detail {
    font-size: 16px;
    background: #DEF1FB;
    border-radius: 12px;
    padding: 8px 16px;
  }
  .ai-detail {
    background: #FFFFFF;
  }
  .chat-img {
    width: 36px;
    height: 36px;
    margin-right: 10px;
  }
  .chat-share-img {
    width: 19px;
    height: 16px;
    position: absolute;
    right: 15px;
  }
}
</style>