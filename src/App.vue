<script setup>
import HeaderItem from '@/components/Header-Item.vue'
import HeaderItemMobile from '@/components/Header-Item-Mobile.vue'
import { useWindowSize } from '@vueuse/core'
const { width } = useWindowSize()
</script>

<template>
  <div class="common-layout">
    <!-- 電腦版 -->
    <template v-if="width > 768">
      <el-container>
        <el-header>
          <HeaderItem />
        </el-header>
        <el-main>Main</el-main>
        <el-footer>Footer</el-footer>
      </el-container>
    </template>
    <!-- 行動版 -->
    <template v-else>
      <el-container>
        <el-header>
          <HeaderItemMobile />
        </el-header>
        <el-main>Main</el-main>
        <el-footer>Footer</el-footer>
      </el-container>
    </template>
  </div>
</template>

<style scoped>
.el-header{
  padding: 0;
}
</style>
