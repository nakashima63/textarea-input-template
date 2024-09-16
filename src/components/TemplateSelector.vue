<template>
  <div class="TemplateSelector">
    <label for="form-select-template">定型文を選択</label>
    <select v-model="selectedTemplate" id="form-select-template">
      <option value="">定型文を選択してください</option>
      <option
        v-for="template in templates"
        :key="template.id"
        :value="template.value"
      >
        {{ template.title }}
      </option>
    </select>
    <button @click="emitTemplate">適用する</button>
  </div>
</template>
<script setup>
import { ref, defineEmits } from "vue";

// テンプレートのリスト
const templates = ref([
  {
    id: 1,
    title: "今日の天気",
    value: "今日はXX月XX日です。天気はXXです。",
  },
  {
    id: 2,
    title: "あいさつ",
    value: "おはようございます。ただいま起床しました。",
  },
  {
    id: 3,
    title: "メールの返信",
    value: "お世話になっております。XXです。",
  },
]);

const selectedTemplate = ref("");

const emit = defineEmits(["selectTemplate"]);

const emitTemplate = () => {
  if (selectedTemplate.value) {
    emit("selectTemplate", selectedTemplate.value);
  }
};
</script>
