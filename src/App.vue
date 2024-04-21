<template>
  <div id="app">
    <template v-if="route.path.startsWith('/user')">
      <router-view />
    </template>
    <template v-else>
      <BasicLayout />
    </template>
  </div>
</template>

<style>
#app {
}
</style>
<script setup lang="ts">
import BasicLayout from "@/layouts/BasicLayout.vue";
import { onMounted } from "vue";
import { useRoute } from "vue-router";

const route = useRoute();
/**
 * todo 全局初始化函数，有全局单次调用的代码，都可以写到这里
 */
const doInit = () => {
  console.log(
    "         .__               .__ \n" +
      "___  __|__|_  _  __ ____ |__|\n" +
      "\\  \\/  /  \\ \\/ \\/ // __ \\|  |\n" +
      " >    <|  |\\     /\\  ___/|  |\n" +
      "/__/\\_ \\__| \\/\\_/  \\___  >__|\n" +
      "      \\/               \\/    "
  );
};

onMounted(() => {
  doInit();
});
</script>
