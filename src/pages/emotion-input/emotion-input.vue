<template>
  <view class="emotion-input">
    <textarea
      v-model="emotionText"
      placeholder="请输入你的情绪日记（200字以内）"
      maxlength="200"
    ></textarea>
    <button @click="submitEmotion">提交</button>
  </view>
</template>

<script>
export default {
  data() {
    return {
      emotionText: ''
    }
  },
  methods: {
    submitEmotion() {
      if (this.emotionText.trim() === '') {
        uni.showToast({
          title: '请输入情绪日记',
          icon: 'none'
        });
        return;
      }
      // TODO: 实现情绪分析逻辑
      console.log('提交的情绪日记:', this.emotionText);
      uni.navigateTo({
        url: '/pages/analysis-result/analysis-result'
      });
    }
  }
}
</script>

<style>
.emotion-input {
  padding: 20rpx;
}

textarea {
  width: 100%;
  height: 300rpx;
  border: 1px solid #ccc;
  border-radius: 5rpx;
  padding: 10rpx;
  margin-bottom: 20rpx;
}

button {
  width: 100%;
}
</style>