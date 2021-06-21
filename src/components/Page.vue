<template>
  <div class="page-main">
    <keep-alive>
      <!-- 必须指定 key 为 fullPath -->
      <router-view :key="$route.fullPath" />
    </keep-alive>
  </div>
</template>

<script>
export default {
  name: 'Page',
};
</script>

<style scoped></style>
