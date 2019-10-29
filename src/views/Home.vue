<template>
  <div class="home">
    <div class="content">
      <div class="home_header">
        <router-link class="link" to="/home">
          <img class="home_logo" src="../assets/userLogo.jpeg" alt="amei logo" />
        </router-link>
      </div>
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
    }
  }
}
</style>
