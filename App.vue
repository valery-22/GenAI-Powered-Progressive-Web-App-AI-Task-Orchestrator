<script setup lang="ts">
import { ref } from 'vue';
import AIAgentChat from './components/AIAgentChat.vue';

const activeTab = ref<'task' | 'sales' | 'service'>('task');
</script>

<template>
  <div class="min-h-screen bg-gray-950 text-white p-6">
    <div class="max-w-4xl mx-auto">
      <h1 class="text-4xl font-bold mb-2">AutoForge</h1>
      <p class="text-sky-400 mb-8">GenAI Agents • Task • Sales • Service • Offline-First PWA</p>

      <div class="flex gap-2 mb-8 border-b border-gray-800">
        <button @click="activeTab = 'task'" :class="{ 'border-b-2 border-sky-400': activeTab === 'task' }" class="px-6 py-3">Task Orchestrator</button>
        <button @click="activeTab = 'sales'" :class="{ 'border-b-2 border-sky-400': activeTab === 'sales' }" class="px-6 py-3">Sales Insights</button>
        <button @click="activeTab = 'service'" :class="{ 'border-b-2 border-sky-400': activeTab === 'service' }" class="px-6 py-3">Customer Service</button>
      </div>

      <AIAgentChat :mode="activeTab" />
    </div>
  </div>
</template>