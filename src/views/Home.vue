<template>
  <div class="mark">
    <img src="../assets/home/pinterest.png" class="mark-img">
  </div>
  <div class="home-content">
    <img src="../assets/home/group.png" class="home-content-img"/>
    <div class="home-upload">
      <a-upload
        v-model:file-list="fileList"
        action="https://www.mocky.io/v2/5cc8019d300000980a055e76"
        @change="handleChange"
        :before-upload="beforeUpload"
      >
        <div class="home-upload-border">
          <img src="../assets/home/upload.png" class="home-upload-img"/>
          <div class="home-upload-text">Upload your patents here.</div>
          <div >You may upload  1 or multiple patents at the  same  time.</div>
        </div>
      </a-upload>
    </div>
  </div>  
</template>
<script  lang="ts">
import { ref } from 'vue';
import { message } from 'ant-design-vue';
export default {
  setup() {
    const fileList = ref([]);
    return {
      fileList
    };
  },
  methods: {
    handleChange(info) {
      const { status } = info.file;
      if (status === 'done') {
        message.success('File uploaded successfully.');
      } else if (status === 'error') {
        message.error('File upload failed.');
      }
    },
    beforeUpload(file) {
      const  isdocx_pdf= file.name.endsWith('.docx') || file.name.endsWith('.doc') || file.name.endsWith('.pdf');
      if (!isdocx_pdf) {
        message.error('Error occured. Please upload DOCX or PDF files only.');
      }
      return isdocx_pdf;
    }
  }
}
</script>
<style >
:where(.css-dev-only-do-not-override-1hsjdkk).ant-upload-wrapper .ant-upload-list {
  display: none !important;
  visibility: hidden !important;
}
.mark {
  display: flex;
  align-items: center;
  margin: 10px 0 0 20px;
  .mark-img {
    width: 300px;
    height: 40px;
  }
}
.home-content {
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  padding-top: 200px;
  position: relative;
  .home-content-img {
    width: 40vw;
  }
  .home-upload {
    display: flex;
    justify-content: center;
  }
  .my-custom-class {
    height: 60px;
    font-size: 20px;
    width: 80%;
    margin-top: 40px;
    border-radius: 20px;
    box-shadow: 1px 5px 30px rgba(0, 0, 0, 0.1);
  }
  .home-upload-border {
    border: 1px solid #E8E3FF;
    box-shadow: 5px 5px 5px #E8E3FF;
    border-radius: 20px;
    width: 80vw;
    height: 160px;
    display: flex;
    align-items: center;
    flex-direction: column;
    margin-top: 66px;
    font-size: 16px;
  }
  .home-upload-img {
    width: 42px;
    height: 42px;
    margin-top: 15px;
  }
  .home-upload-text {
    margin: 20px 0 6px;
  }
}
</style>
