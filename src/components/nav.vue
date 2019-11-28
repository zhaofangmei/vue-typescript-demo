<template>
  <div>
    <el-row>
      <el-col :span="4"></el-col>
      <el-col :span="16">
        <el-menu
          :default-active="activeIndex"
          class="el-menu-demo"
          mode="horizontal"
          @select="handleSelect"
        >
          <el-menu-item v-for="item in menuList" :key="item.index" :index="item.index">{{item.name}}</el-menu-item>
        </el-menu>
      </el-col>
      <el-col :span="4"></el-col>
    </el-row>
  </div>
</template>
<script lang="ts">
import { Vue, Component, Watch } from "vue-property-decorator";

@Component
export default class Nav extends Vue {
  private activeIndex: string = "1";
  private menuList: Array<Object> = [
    { index: "1", name: "首页", path: "/" },
    { index: "2", name: "文章", path: "/articles" },
    { index: "3", name: "归档", path: "/archive" },
    { index: "4", name: "项目", path: "/project" },
    { index: "5", name: "历程", path: "/timeline" },
    { index: "6", name: "留言", path: "/message" },
    { index: "7", name: "关于", path: "/about" }
  ];
  private handleSelect(key: string, keyPath: string): void {
    this.activeIndex = key;
  }
}
</script>
<style lang="less" scoped>
</style>