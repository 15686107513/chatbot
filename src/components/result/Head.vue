<template>
  <div class="head">
    <img src="../../assets/result/menu.png" class="result-menu"/>
    <div class="head-wrap">
      <div class="result-search">
        <img src="../../assets/result/plus.png" class="result-plus"/>
        New Search
      </div>
      <div class="result-search result-list">
        My List
        <div class="result-number">1</div>
      </div>
      <img src="../../assets/result/share.png" class="result-share"/>
    </div>
  </div>
</template>

<style>
.head {
  display: flex;
  justify-content: space-between;
  padding-top: 10px;
}
.result-menu {
  width: 24px;
  height: 24px;
  margin: 0px 0 0 20px;
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
</style>
