<template>
  <div class="TextAreaWithTemplate">
    <TemplateSelector @selectTemplate="handleTemplateSelection" />
    <TextArea
      :content="textareaContent"
      @updateContent="textareaContent = $event"
    />
  </div>
</template>

<script setup>
import { ref } from "vue";
import TemplateSelector from "./TemplateSelector.vue";
import TextArea from "./TextArea.vue";

// テキストエリアの内容
const textareaContent = ref("");

// 定型文選択時の処理
const handleTemplateSelection = (selectedTemplate) => {
  textareaContent.value = selectedTemplate;
};
</script>
