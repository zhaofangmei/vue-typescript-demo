<template>
  <div class="nav">
    <el-row :gutter="24">
      <!-- logo -->
      <el-col :span="3">
        <router-link to="/">
          <img class="logo" src="../assets/userLogo.jpg" alt="amei logo" />
        </router-link>
      </el-col>
      <!-- 导航列表 -->
      <el-col :span="16">
        <el-menu
          :router="true"
          :default-active="activeIndex"
          class="el-menu-demo"
          mode="horizontal"
          @select="handleSelect"
        >
          <el-menu-item
            v-for="item in menuList"
            :key="item.index"
            :index="item.index"
            :route="item.path"
          >{{item.name}}</el-menu-item>
        </el-menu>
      </el-col>
      <!-- 按钮 -->
      <el-col :span="5">
        <div></div>
        <div>
          <el-button size="small" type="primary" @click="handleClick('login')">登录</el-button>
          <el-button size="small" type="danger" @click="handleClick('register')">注册</el-button>
        </div>
      </el-col>
    </el-row>
    <!-- 登录注册弹框 -->
    <RegisterAndLogin :dialogType="dialogType" :dialogVisible="dialogVisible"></RegisterAndLogin>
  </div>
</template>
<script lang="ts">
import { Vue, Component, Watch } from "vue-property-decorator";
import { Route } from "vue-router";
import { navListItem } from "@/types/index";
import RegisterAndLogin from "@/components/registerAndLogin.vue";

@Component({
  components: {
    RegisterAndLogin
  }
})
export default class Nav extends Vue {
  private dialogType: string = "";
  private dialogVisible: boolean = false;
  private menuList: Array<navListItem> = [
    { index: "1", name: "首页", path: "/" },
    { index: "2", name: "文章", path: "/articles" },
    { index: "3", name: "归档", path: "/archive" },
    { index: "4", name: "项目", path: "/project" },
    { index: "5", name: "历程", path: "/timeline" },
    { index: "6", name: "留言", path: "/message" },
    { index: "7", name: "关于", path: "/about" }
  ];
  private activeIndex: string = "1";
  private handleSelect(key: string, keyPath: string): void {
    this.activeIndex = key;
  }
  mounted() {
    this.routeChage(this.$route, this.$route);
  }
  handleClick(type: string): void {
    this.dialogVisible = true;
    this.dialogType = type;
  }
  routeChage(val: Route, oldVal: Route): void {
    this.menuList.map(item => {
      if (val.path == item.path) {
        this.activeIndex = item.index;
      }
    });
  }
}
</script>
<style lang="less" scoped>
.nav {
  .logo {
    height: 50px;
    width: 50px;
    border-radius: 50%;
  }
}
</style>