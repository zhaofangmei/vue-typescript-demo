<template>
  <div id="app" class="container">
    <Nav v-if="isShowNav"></Nav>
    <div class="layout">
      <router-view />
    </div>
    <div v-if="isShowNav">typescript+vue ©2019 Created by amei</div>
  </div>
</template>
<script lang="ts">
import { Vue, Component, Watch } from "vue-property-decorator";
import { Route } from "vue-router";
import Nav from "@/components/nav.vue";

@Component({
  components: { Nav }
})
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
@import url("./less/index.less");
@import url("./less/mobile.less");
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  width: 1200px;
  margin: 0 auto;
}
.container {
  height: calc(100vh - 20px);
  max-height: 100vh;
  overflow: hidden;
}
.layout {
  background-color: #ccc;
}
</style>
