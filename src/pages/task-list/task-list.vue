<template>
  <view class="task-list">
    <text class="title">每日任务</text>
    <view v-for="(task, index) in tasks" :key="index" class="task-item">
      <text>{{ task.name }}</text>
      <switch :checked="task.completed" @change="toggleTask(index)"></switch>
    </view>
  </view>
</template>

<script>
export default {
  data() {
    return {
      tasks: [
        { name: '记录今天的情绪', completed: false },
        { name: '做15分钟冥想', completed: false },
        { name: '与朋友聊天', completed: false },
        { name: '运动30分钟', completed: false }
      ]
    }
  },
  methods: {
    toggleTask(index) {
      this.tasks[index].completed = !this.tasks[index].completed;
    }
  }
}
</script>

<style>
.task-list {
  padding: 20rpx;
}

.title {
  font-size: 36rpx;
  font-weight: bold;
  text-align: center;
  margin-bottom: 30rpx;
}

.task-item {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 20rpx 0;
  border-bottom: 1px solid #eee;
}
</style>