<template>
  <textarea
    v-model="localContent"
    rows="10"
    cols="50"
    @input="updateContent"
  ></textarea>
</template>

<script setup>
import { ref, watch, defineProps, defineEmits } from "vue";

// 親から受け取るプロパティ
const props = defineProps({
  content: {
    type: String,
    required: true,
  },
});

// emit関数の定義
const emit = defineEmits(["updateContent"]);

const localContent = ref(props.content);

// 親コンポーネントに変更を通知
const updateContent = () => {
  emit("updateContent", localContent.value);
};

// 親コンポーネントのcontentが更新されたらテキストエリアの入力内容を更新
watch(
  () => props.content,
  (newContent) => {
    localContent.value = newContent;
  }
);
</script>

<style>
textarea {
  width: 100%;
  padding: 10px;
  font-size: 16px;
}
</style>
