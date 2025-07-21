<template>
  <view class="container">
    <image class="logo" src="/static/logo.png" />
    <view class="title">播报页面</view>
  </view>
</template>

<script>
export default {
  name: 'BroadcastPage',
};
</script>

<style>
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100vh;
}
.logo {
  width: 120rpx;
  height: 120rpx;
  margin-bottom: 30rpx;
}
.title {
  font-size: 32rpx;
  color: #e94f4f;
}
</style>
