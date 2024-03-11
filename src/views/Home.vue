<template>
  <div class="mark">
    <img src="../assets/home/pinterest.png" class="mark-img">
    <span class="mark-title">sponser</span>
  </div>
  <div class="home-content">
    <img src="../assets/home/group.png" class="home-content-img"/>
    <a-input
      class="my-custom-class"
      v-model:value="textVal"
      placeholder="what do you want to search for today?"
      @pressEnter="send"
    />
    <img src="../assets/home/guide.png" class="home-content-printerest" @click="send"/>
  </div>  
</template>
<script  lang="ts">
import { ref } from 'vue';
export default {
  setup() {
    const textVal = ref('');
    return {
      textVal
    };
  },
  methods: {
    send() {
      if(this.textVal) {
        this.textVal = '';
        // 请求接口
        // this.$router.push({path: '/backend/order', query: {selected: "2"}});
      }
    }
  }
}
</script>
<style scoped>
.mark {
  display: flex;
  align-items: center;
  margin: 10px 0 0 20px;
  .mark-img {
    width: 52px;
    height: 54px;
  }
  .mark-title {
    color: #000;
    font-size: 20px;
    font-weight: 600;
  }
  
}
.home-content {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  padding-top: 200px;
  position: relative;
  .home-content-img {
    width: 665px;
    height: 250px;
  }
  .home-content-printerest {
    position: absolute;
    right: 20px;
    bottom: 45px;
  }
  .my-custom-class {
    height: 60px;
    font-size: 20px;
    width: 80%;
    margin-top: 40px;
    border-radius: 20px;
  }
  .home-content-printerest {
    position: absolute;
    bottom: 14px;
    right: 160px;
    width: 23px;
    height: 24px;
  }
}
</style>
