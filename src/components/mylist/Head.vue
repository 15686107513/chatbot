<template>
  <div class="head">
    <img src="../../assets/result/menu.png" class="result-menu"/>
    <div class="head-wrap">
      <div class="result-search">
        Export
      </div>
      <img src="../../assets/result/share.png" class="result-share"/>
    </div>
  </div>
</template>

<style>
.head {
  display: flex;
  justify-content: space-between;
  padding: 10px 0;
  align-items: center;
  border-bottom: 1px solid #B2B6BC;
} 
.result-menu {
  width: 24px;
  height: 24px;
  margin: 0px 0 0 20px;
}
.result-search {
  width: 120px;
  height: 36px;
  background: #1D9BD1;
  color: #fff;
  border-radius: 6px;
  display: flex;
  justify-content: center;
  align-items: center;
  margin-right: 12px;
}
.result-share {
  width: 28px;
  height: 28px;
}
.head-wrap {
  display: flex;
  align-items: center;
  position: relative;
  right: 30px;
}
</style>
