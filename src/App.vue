<script setup>
import { reactive } from 'vue'

const data = reactive({
  greeting: 'Hello World!'
})
const rules = {
  greeting: [{ required: true }],
}
</script>

<template>
  <el-card>
    <template #header>
      <h1>Validation Warnings Minimal Reproduction</h1>
    </template>
    <ol>
      <li>Open the browser console</li>
      <li>Clear the text from the "Greeting" input</li>
      <li>Click away from the input</li>
    </ol>
    <el-form
      :model="data"
      :rules>
      <el-form-item
        prop="greeting"
        label="Greeting">
        <el-input
          v-model="data.greeting"
        />
      </el-form-item>
    </el-form>
  </el-card>
</template>

<style>
:root {
  background-color: var(--el-bg-color-page);
  font-family: var(--el-font-family);
  font-size: var(--el-font-size-base);
}
#app {
  max-width: max-content;
  margin: 0 auto;
}
</style>

<style scoped>
h1 {
  font-size: var(--el-font-size-extra-large);
  margin: 0;
}

ol {
  color: var(--el-text-color-regular);
  margin-top: 0;
  padding-left: 1rem;
}
</style>