<template>
  <div class="code-block-wrapper">
    <button class="copy-button" @click="copyCode" aria-label="Copy code">
      <svg v-if="!copied" xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" viewBox="0 0 16 16" class="copy-icon">
        <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path>
        <path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
      </svg>
      <svg v-else xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" viewBox="0 0 16 16" class="copy-icon">
        <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
      </svg>
    </button>
    <slot />
  </div>
</template>

<script setup>
import { ref } from 'vue';

const copied = ref(false);

function copyCode() {
  const code = document.querySelector('.code-block-wrapper pre code')?.innerText;
  if (code) {
    navigator.clipboard.writeText(code);
    copied.value = true;
    
    setTimeout(() => {
      copied.value = false;
    }, 2000);
  }
}
</script>

<style scoped>
.copy-button svg {
  transition: fill 0.3s;
}

.copy-icon {
  fill: #ccc;
  width: 20px;
  height: 20px;
}

.code-block-wrapper {
  position: relative;
}

.copy-button {
  position: absolute;
  top: 0.5rem;
  right: 0.5rem;
  background: none;
  border: none;
  cursor: pointer;
  padding: 0.2rem;
  z-index: 10;
}

.copy-button:hover .copy-icon {
  fill: #43a069;
}
</style>
