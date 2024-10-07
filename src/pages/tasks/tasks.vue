<template>
  <view class="container">
    <text class="page-title">每日任务</text>
    <view class="task-list">
      <view v-for="(task, index) in tasks" :key="index" class="task-item">
        <checkbox :checked="task.completed" @click="toggleTask(index)" />
        <text :class="{ 'task-text': true, 'completed': task.completed }">{{ task.text }}</text>
      </view>
    </view>
  </view>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue'

interface Task {
  text: string
  completed: boolean
}

export default defineComponent({
  name: 'TasksPage',
  setup() {
    const tasks = ref<Task[]>([
      { text: '记录今天的心情', completed: false },
      { text: '做15分钟冥想', completed: false },
      { text: '与朋友聊天', completed: false },
      { text: '运动30分钟', completed: false },
      { text: '阅读一章积极心理学的书', completed: false },
    ])

    const toggleTask = (index: number) => {
      tasks.value[index].completed = !tasks.value[index].completed
    }

    return {
      tasks,
      toggleTask
    }
  }
})
</script>

<style>
.container {
  padding: 20px;
}

.page-title {
  font-size: 24px;
  font-weight: bold;
  margin-bottom: 20px;
}

.task-list {
  background-color: #ffffff;
  border-radius: 10px;
  padding: 10px;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
}

.task-item {
  display: flex;
  align-items: center;
  padding: 10px 0;
  border-bottom: 1px solid #f0f0f0;
}

.task-item:last-child {
  border-bottom: none;
}

.task-text {
  margin-left: 10px;
  font-size: 16px;
}

.completed {
  text-decoration: line-through;
  color: #888;
}
</style>