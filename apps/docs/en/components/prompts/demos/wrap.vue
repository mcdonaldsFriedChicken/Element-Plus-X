<docs>
---
title: Wrapping Display
---

Use the `wrap` attribute to control whether `Prompts` can wrap when exceeding the area length.
</docs>

<script setup lang="ts">
import type { PromptsItemsProps } from 'vue-element-plus-x/types/Prompts';

const items = ref<PromptsItemsProps[]>([
  {
    key: '1',
    label: '🐛 Prompts Component Title',
    description: 'Description information'.repeat(3)
  },
  {
    key: '2',
    label: '🐛 I am disabled',
    disabled: true
  },
  {
    key: '3',
    label: '🐛 Individual disable control is more accurate',
    disabled: true
  },
  {
    key: '4',
    label: '🐛 Prompts Component Title'
  }
]);

function handleItemClick(item: PromptsItemsProps) {
  ElMessage.success(`Clicked ${item.key}`);
}
</script>

<template>
  <div style="display: flex; flex-direction: column; gap: 12px">
    <Prompts
      title="🐵 Prompts Component Title"
      :items="items"
      wrap
      @item-click="handleItemClick"
    />
  </div>
</template>

<style scoped lang="less"></style>
