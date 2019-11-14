<template>
  <div id="app" class="container">
    <div v-if="isShowNav">nav</div>
    <div class="layout">
      <router-view />
    </div>
    <div v-if="isShowNav">typescript+vue ©2019 Created by amei</div>
  </div>
</template>
<script lang="ts">
import { Vue, Component, Watch } from "vue-property-decorator";
import { Route } from "vue-router";

@Component
export default class App extends Vue {
  private isShowNav: boolean = true;
  mounted(): void {
    this.routeChange(this.$route, this.$route);
  }
  @Watch("$route")
  routeChange(val: Route, oldVal: Route): void {
    if (val.path == "/") {
      this.isShowNav = false;
    } else {
      this.isShowNav = true;
    }
  }
}
</script>
<style lang="less">
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
.container {
  height: 100%;
}
.layout {
  height: calc(~"100% - 100px");
}
</style>
