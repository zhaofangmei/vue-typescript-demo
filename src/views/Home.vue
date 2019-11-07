<template>
  <div class="home">
    <div class="content">
      <div class="home_header">
        <router-link class="link" to="/home">
          <img class="home_logo" src="../assets/userLogo.jpg" alt="amei logo" />
        </router-link>
      </div>
      <div class="home_header"></div>
    </div>
  </div>
</template>

<script lang="ts">
export default {
  name: "home",
  components: {}
};
</script>
<style lang="less">
.home {
  .home_header {
    .link {
      display: block;
    }
    .home_logo {
      width: 220px;
      border-radius: 50%;
      animation: mylogo 5s infinite;
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
