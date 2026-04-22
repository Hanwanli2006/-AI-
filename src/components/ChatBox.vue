<template>
  <section class="chat-box">
    <div class="chat-header">
      <h2>AI 电路问答助手</h2>
    </div>

    <div class="messages">
      <div
        v-for="(msg, index) in messages"
        :key="index"
        :class="msg.role"
      >
        {{ msg.content }}
      </div>
    </div>

    <div class="input-area">
      <input
        v-model="userInput"
        @keyup.enter="sendMessage"
        placeholder="请输入电路问题..."
      />

      <button @click="sendMessage">
        发送
      </button>
    </div>
  </section>
</template>

<script setup lang="ts">
import { ref } from 'vue'

const userInput = ref('')

const messages = ref([
  {
    role: 'assistant',
    content: '你好，我是 AI 电路教学助理。'
  }
])

const sendMessage = () => {
  if (!userInput.value.trim()) return

  messages.value.push({
    role: 'user',
    content: userInput.value
  })

  messages.value.push({
    role: 'assistant',
    content: 'AI 正在分析你的电路问题...'
  })

  userInput.value = ''
}
</script>

<style scoped>
.chat-box {
  background: white;
  border-radius: 16px;
  overflow: hidden;
  box-shadow: 0 2px 10px rgba(0,0,0,0.1);
}

.chat-header {
  background: #4338ca;
  color: white;
  padding: 20px;
}

.messages {
  height: 400px;
  overflow-y: auto;
  padding: 20px;
  background: #f9fafb;
}

.user {
  text-align: right;
  margin-bottom: 15px;
  background: #4f46e5;
  color: white;
  padding: 12px;
  border-radius: 12px;
}

.assistant {
  text-align: left;
  margin-bottom: 15px;
  background: #e5e7eb;
  padding: 12px;
  border-radius: 12px;
}

.input-area {
  display: flex;
  padding: 20px;
  gap: 10px;
}

.input-area input {
  flex: 1;
  padding: 12px;
  border-radius: 10px;
  border: 1px solid #ccc;
}

.input-area button {
  background: #4f46e5;
  color: white;
  border: none;
  padding: 12px 24px;
  border-radius: 10px;
  cursor: pointer;
}
</style>