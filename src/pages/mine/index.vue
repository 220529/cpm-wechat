<template>
  <view class="mine-container">
    <view class="header">
      <image class="avatar" src="/static/logo.png" />
      <view class="user-info">
        <view class="name">郑加祥</view>
        <view class="role">项目经理</view>
      </view>
    </view>
    <view class="stats">
      <view class="stat-item">
        <view class="stat-num">329</view>
        <view class="stat-label">已竣工</view>
      </view>
      <view class="stat-item">
        <view class="stat-num">12</view>
        <view class="stat-label">施工中</view>
      </view>
    </view>
    <view class="setting-list">
      <view class="setting-item" @click="goSetting">
        <text>设置</text>
        <text class="arrow">&gt;</text>
      </view>
    </view>
  </view>
</template>

<script>
export default {
  name: 'MinePage',
  methods: {
    goSetting() {
      uni.showToast({ title: '设置', icon: 'none' });
    },
  },
};
</script>

<style>
.mine-container {
  background: #fafafa;
  min-height: 100vh;
}
.header {
  display: flex;
  align-items: center;
  padding: 40rpx 30rpx 20rpx 30rpx;
  background: #fff;
  border-bottom: 1rpx solid #f0f0f0;
}
.avatar {
  width: 100rpx;
  height: 100rpx;
  border-radius: 50%;
  margin-right: 24rpx;
}
.user-info {
  display: flex;
  flex-direction: column;
}
.name {
  font-size: 32rpx;
  font-weight: bold;
  margin-bottom: 8rpx;
}
.role {
  font-size: 24rpx;
  color: #888;
}
.stats {
  display: flex;
  justify-content: flex-start;
  background: #fff;
  padding: 30rpx 0 10rpx 0;
  border-bottom: 1rpx solid #f0f0f0;
}
.stat-item {
  flex: 0 0 120rpx;
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-right: 60rpx;
}
.stat-num {
  font-size: 36rpx;
  font-weight: bold;
  color: #222;
}
.stat-label {
  font-size: 24rpx;
  color: #888;
}
.setting-list {
  margin-top: 20rpx;
  background: #fff;
}
.setting-item {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 28rpx 30rpx;
  font-size: 30rpx;
  border-bottom: 1rpx solid #f0f0f0;
  background: #d6f5e3;
}
.arrow {
  color: #bbb;
  font-size: 32rpx;
}
</style>
