<template>
  <div id="app">
    <a-space direction="vertical">
      <div v-if="hasNotice">
        <a-alert message="收到传递过来的信息" type="success" show-icon />
        {{ $root.noticeState }}
      </div>
      <div v-else>暂无传递的数据</div>

      <a-button @click="getApi">请求接口</a-button>
    </a-space>
  </div>
</template>

<script>
import { getRoutesConfig } from '@/api/user';

export default {
  name: 'Home',
  components: {},
  data() {
    return { title: '' };
  },
  computed: {
    hasNotice() {
      return this.$root.noticeState.length > 0;
    },
  },
  mounted() {},
  methods: {
    async getApi() {
      const data = await getRoutesConfig();
      this.$message.success(`接口请求成功: ${JSON.stringify(data)}`);
    },
  },
};
</script>

<style lang="less" scoped>
#app {
  img {
    width: 50px;
    height: 50px;
  }
}
</style>
