<template>
  <div class="page-index">
    <el-row>
      <el-col :span="5">1</el-col>
      <el-col :span="19">2</el-col>
    </el-row>
    <el-row>
      <el-col :span="24">3</el-col>
    </el-row>
  </div>
</template>

<script>
import Logo from '~/components/Logo.vue'

export default {
  components: {
    Logo
  }
}
</script>

<style lang="scss">
@import "@/assets/css/index/index.scss";
</style>
