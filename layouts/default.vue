<template>
  <el-container class="layout-default">
    <el-header style="height: 100%">
      <my-header></my-header>
    </el-header>
    <el-main>
      <div>
        <nuxt />
      </div>
    </el-main>
    <el-footer>Footer</el-footer>
  </el-container>
</template>
<script>
import MyHeader from '@/components/header/index.vue'
export default {
  components: { 
    MyHeader
  }
}
</script>

<style></style>
