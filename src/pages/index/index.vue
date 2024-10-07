<template>
  <view class="content">
    <image class="logo" src="/static/logo.png"></image>
    <view class="text-area">
      <text class="title">{{title}}</text>
    </view>
    <view class="nav-buttons">
      <button @click="navigateTo('/pages/emotion-input/emotion-input')">记录情绪</button>
      <button @click="navigateTo('/pages/task-list/task-list')">任务列表</button>
    </view>
  </view>
</template>

<script>
export default {
  data() {
    return {
      title: '欢迎来到情绪小狐狸'
    }
  },
  methods: {
    navigateTo(url) {
      uni.navigateTo({
        url: url
      });
    }
  }
}
</script>

<style>
.content {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

.logo {
  height: 200rpx;
  width: 200rpx;
  margin-top: 200rpx;
  margin-left: auto;
  margin-right: auto;
  margin-bottom: 50rpx;
}

.text-area {
  display: flex;
  justify-content: center;
}

.title {
  font-size: 36rpx;
  color: #8f8f94;
}

.nav-buttons {
  margin-top: 50rpx;
}

button {
  margin: 20rpx 0;
}
</style>