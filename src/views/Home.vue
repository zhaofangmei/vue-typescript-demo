<template>
  <div class="home">
    <div class="content">
      <div class="home_header">
        <router-link class="link" to="/home">
          <img class="home_logo" src="../assets/userLogo.jpg" alt="amei logo" />
        </router-link>
      </div>
      <div class="home_body">
        <div class="list">
          <router-link class="link" to="/articles">文章</router-link>
          <router-link class="link" to="/project">项目</router-link>
          <a
            target="_blank"
            rel="noopener noreferrer"
            class="link"
            href="https://github.com/zhaofangmei"
          >github</a>
        </div>
        <div class="introduce">时光正好，未来可期，加油 ！</div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { Vue, Component, Watch } from "vue-property-decorator";

@Component
export default class Home extends Vue {}
</script>
<style lang="less" scoped>
.home {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  .content {
    flex: 1;
    font-size: 20px;
    text-align: center;
  }
  .home_header {
    .link {
      display: inline-block;
    }
    .home_logo {
      width: 220px;
      border-radius: 50%;
      animation: mylogo 5s infinite;
    }
  }
  .home_body {
    padding-top: 20px;
    .list .link {
      display: inline-block;
      padding: 20px;
      color: #409eff;
    }
  }
}
@keyframes mylogo {
  0% {
    transform: scale(0.7, 0.7);
  }
  25% {
    transform: scale(1, 1);
  }
  100% {
    transform: scale(0.7, 0.7);
  }
}
</style>
