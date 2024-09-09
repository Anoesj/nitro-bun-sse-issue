<template>
  <div>
    <button @click="startSse">Start SSE</button>
    <button @click="cancelSse">Cancel SSE</button>
  </div>
</template>

<script setup lang="ts">
let eventSource: EventSource | undefined;

function startSse() {
  eventSource = new EventSource('/api/sse');

  eventSource.onmessage = (event) => {
    console.log('Event received:', event.data);
  };

  eventSource.onerror = (error) => {
    console.error('SSE error:', error);
  };
}

function cancelSse() {
  if (eventSource) {
    console.log('Closing SSE connection');
    eventSource.close();
  }
}
</script>
