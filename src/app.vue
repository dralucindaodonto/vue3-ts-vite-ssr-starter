<template>
  <el-menu active-text-color="white" text-color="white" background-color="#387dff" mode="horizontal" router>
    <div class="mt-15px" style="z-index: 10">
      <el-image style="width: 35px; height: 35px" src="https://dentaldesk.com.br/drawings/logopngwhite.svg" />
    </div>

    <div class="mt-20px text-white">Dentaldesk</div>

    <el-menu-item index="/">1</el-menu-item>
    <el-menu-item index="user">2</el-menu-item>
    <el-menu-item index="market">3</el-menu-item>
  </el-menu>

  <div class="container" style="top: 20px">
    <router-view v-slot="{ Component }">
      <Suspense>
        <component :is="Component" />
      </Suspense>
    </router-view>
  </div>
</template>

<script lang="ts">
export default defineComponent({
  name: 'App',
  data() {
    return {
      time: ''
    };
  },
  mounted() {
    window.setInterval(() => {
      this.time = new Date().toLocaleString();
    }, 1000);
  }
});
</script>
<style scoped>
.el-menu--horizontal {
  border-bottom: none;
  border-right: none;
}
.logo {
  text-align: center;
}

nav {
  width: 500px;
  display: flex;
  justify-content: space-between;
  margin: 0 auto;
  padding: 20px 0;
  border-radius: 4px;
}
</style>
