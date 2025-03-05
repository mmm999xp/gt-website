<script setup>
import HeaderItem from '@/components/Header-Item.vue'

</script>

<template>
  <div class="common-layout">
    <el-container>
      <el-header>
        <HeaderItem />
      </el-header>
      <el-main>Main</el-main>
      <el-footer>Footer</el-footer>
    </el-container>
  </div>
</template>

<style scoped>
.el-header{
  padding: 0;
}
</style>
