<template>
  <view class="login-container">
    <image class="logo" src="/static/logo.png" />
    <view class="title">天坛定装</view>
    <view class="subtitle">TINTAN</view>
    <view class="form">
      <input v-model="phone" class="input" type="text" placeholder="请输入手机号" />
      <input v-model="password" class="input" type="password" placeholder="请输入密码" />
      <view v-if="errorMsg" class="error-msg">
        <text>❌ {{ errorMsg }}</text>
      </view>
      <button class="login-btn" :disabled="!canLogin" @click="handleLogin">立即登录</button>
      <view class="protocol">
        <checkbox :checked="checked" @change="checked = $event.detail.value.length > 0" />
        <text>我已阅读并同意</text>
        <text class="link" @click="goToUserAgreement">《用户协议》</text>
        <text>和</text>
        <text class="link" @click="goToPrivacyPolicy">《隐私政策》</text>
      </view>
    </view>
  </view>
</template>

<script>
export default {
  name: 'LoginPage',
  data() {
    return {
      phone: '',
      password: '',
      checked: false,
      errorMsg: '',
    };
  },
  computed: {
    canLogin() {
      return this.phone && this.password && this.checked;
    },
  },
  methods: {
    handleLogin() {
      if (!this.checked) {
        this.errorMsg = '请阅读并同意用户协议和隐私政策，并确认勾选';
        return;
      }
      if (this.phone !== '测试手机号' || this.password !== '88888888') {
        this.errorMsg = '密码错误，请确认后重新输入';
        return;
      }
      this.errorMsg = '';
      // 模拟登录接口
      console.log('登录请求', { phone: this.phone, password: this.password });
      // 登录成功后跳转首页
      uni.switchTab({ url: '/pages/index/index' });
    },
    goToUserAgreement() {
      uni.showToast({ title: '跳转用户协议', icon: 'none' });
    },
    goToPrivacyPolicy() {
      uni.showToast({ title: '跳转隐私政策', icon: 'none' });
    },
  },
};
</script>

<style>
.login-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 60rpx 30rpx 0 30rpx;
}
.logo {
  width: 160rpx;
  height: 160rpx;
  margin-bottom: 30rpx;
}
.title {
  font-size: 48rpx;
  font-weight: bold;
  margin-bottom: 10rpx;
  color: #e94f4f;
}
.subtitle {
  font-size: 28rpx;
  color: #e94f4f;
  margin-bottom: 40rpx;
}
.form {
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
}
.input {
  width: 100%;
  height: 80rpx;
  margin-bottom: 20rpx;
  border: 1rpx solid #e0e0e0;
  border-radius: 8rpx;
  padding: 0 20rpx;
  font-size: 32rpx;
  background: #fff;
}
.login-btn {
  width: 100%;
  height: 80rpx;
  background: #1890ff;
  color: #fff;
  font-size: 32rpx;
  border-radius: 8rpx;
  margin: 20rpx 0;
}
.protocol {
  display: flex;
  align-items: center;
  font-size: 24rpx;
  color: #888;
}
.link {
  color: #1890ff;
  margin: 0 4rpx;
}
.error-msg {
  color: #e94f4f;
  font-size: 26rpx;
  margin-bottom: 10rpx;
  width: 100%;
  text-align: left;
}
</style>
