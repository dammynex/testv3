<script lang="ts" setup>
import { onMounted, ref, watch } from "nativescript-vue";

const text = ref("");
const tf = ref(null);

onMounted(() => {
  watch(text, (val) => console.log(val));
});
</script>

<template>
  <Page>
    <StackLayout>
      <Label :text="text" textWrap="true" />
      <TextField
        class="p-5 bg-gray-100"
        ref="tf"
        hint=""
        :text="text"
        @textChange="($event) => (text = $event.object.text)"
      />
    </StackLayout>
  </Page>
</template>