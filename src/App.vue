<template>
  <div id="app" class="container">
    <el-container>
      <el-header></el-header>
      <el-main class="layout">
        <router-view />
      </el-main>
      <el-footer></el-footer>
    </el-container>
  </div>
</template>

<style lang="less">
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
