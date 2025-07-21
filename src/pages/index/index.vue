<template>
  <view class="home-container">
    <view class="card project-card">
      <image class="project-icon" src="/static/logo.png" />
      <view class="project-title">项目管理</view>
    </view>
    <view class="todo-section">
      <view class="todo-title">我的待办</view>
      <view class="todo-grid">
        <view v-for="item in todoList" :key="item.label" class="todo-item">
          <view class="todo-label">{{ item.label }}</view>
          <view class="todo-count">{{ item.count }}<text class="arrow">&gt;</text></view>
        </view>
      </view>
    </view>
  </view>
</template>

<script>
export default {
  name: 'HomePage',
  data() {
    return {
      todoList: [
        { label: '任务包验收', count: 4 },
        { label: '材料变更', count: 4 },
        { label: '缺货补货', count: 0 },
        { label: '节点验收', count: 4 },
        { label: '节点验收整改', count: 1 },
        { label: '任务包延期', count: 1 },
      ],
    };
  },
};
</script>

<style>
.home-container {
  background: #fafafa;
  min-height: 100vh;
  padding: 20rpx 0 0 0;
}
.card.project-card {
  display: flex;
  align-items: center;
  background: #fff;
  border-radius: 16rpx;
  margin: 20rpx 16rpx 0 16rpx;
  padding: 32rpx 24rpx;
  box-shadow: 0 2rpx 8rpx #f0f1f2;
}
.project-icon {
  width: 64rpx;
  height: 64rpx;
  margin-right: 20rpx;
}
.project-title {
  font-size: 32rpx;
  font-weight: bold;
  color: #333;
}
.todo-section {
  background: #fff;
  border-radius: 16rpx;
  margin: 24rpx 16rpx 0 16rpx;
  padding: 24rpx 24rpx 32rpx 24rpx;
}
.todo-title {
  font-size: 28rpx;
  font-weight: bold;
  margin-bottom: 20rpx;
  color: #222;
}
.todo-grid {
  display: flex;
  flex-wrap: wrap;
  gap: 20rpx 16rpx;
}
.todo-item {
  width: 46%;
  background: #f5f5f5;
  border-radius: 10rpx;
  padding: 24rpx 0 24rpx 24rpx;
  margin-bottom: 16rpx;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.todo-label {
  font-size: 28rpx;
  color: #333;
}
.todo-count {
  font-size: 28rpx;
  color: #888;
  display: flex;
  align-items: center;
}
.arrow {
  font-size: 28rpx;
  color: #bbb;
  margin-left: 4rpx;
}
</style>
