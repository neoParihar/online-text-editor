<template>
  <div class="editor-container">
    <div class="toolbar">
      <button @click="format('bold')">Bold</button>
      <button @click="format('italic')">Italic</button>
      <button @click="format('underline')">Underline</button>
    </div>

    <div class="editor" contenteditable="true" ref="editor"></div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const editor = ref(null)

function format(command) {
  document.execCommand(command, false, null)
}
</script>

<style scoped>
.editor-container {
  max-width: 600px;
  margin: 20px auto;
  font-family: Arial, sans-serif;
}

.toolbar {
  display: flex;
  gap: 10px;
  margin-bottom: 10px;
}

.toolbar button {
  padding: 5px 10px;
  font-size: 14px;
  cursor: pointer;
}

.editor {
  min-height: 200px;
  border: 1px solid #ccc;
  padding: 10px;
  outline: none;
}
</style>
