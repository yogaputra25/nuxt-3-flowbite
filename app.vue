<script setup>
import { onMounted } from "vue";
import { FwbButton, FwbModal } from "flowbite";

// initialize components based on data attribute selectors
onMounted(() => {
  initFlowbite();
});
</script>

<template>
  <div>
    <NuxtPage></NuxtPage>
  </div>
</template>
