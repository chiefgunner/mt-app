<template>
  <el-container class="layout-default">
    <el-header height="197px">
      <the-header />
    </el-header>
    <el-main>
      <nuxt />
    </el-main>
    <el-footer height="100%">
      <the-footer />
    </el-footer>
  </el-container>
</template>

<script>
import TheHeader from '@/components/public/header/index'
import TheFooter from '@/components/public/footer/index'
export default {
  components: {
    TheHeader,
    TheFooter
  }
}
</script>
<style lang="scss">
@import "@/assets/css/public/layout.scss";
</style>
