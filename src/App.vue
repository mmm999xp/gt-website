<script setup>
import HeaderItem from '@/components/Header-Item.vue'
import HeaderItemMobile from '@/components/Header-Item-Mobile.vue'
import HomeItem from '@/components/Home-Item.vue'
import AboutItem from '@/components/About-Item.vue'
import ServicesItem from '@/components/Services-Item.vue'
import ContactItem from './components/Contact-Item.vue'
import FooterItem from './components/Footer-Item.vue'
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
        <el-main>
          <HomeItem id="home" />
          <AboutItem id="about" />
          <ServicesItem id="services" />
          <ContactItem id="contact" />
        </el-main>
        <el-footer><FooterItem /></el-footer>
      </el-container>
    </template>
    <!-- 行動版 -->
    <template v-else>
      <el-container>
        <el-header>
          <HeaderItemMobile />
        </el-header>
        <el-main>
          <HomeItem id="home" />
          <AboutItem id="about" />
          <ServicesItem id="services" />
          <ContactItem id="contact" />
        </el-main>
        <el-footer><FooterItem /></el-footer>
      </el-container>
    </template>
  </div>
</template>

<style scoped>
.el-header{
  padding: 0;
  position: fixed;
  width: 100%;
  z-index: 10;
}
.el-main{
  margin-top: 60px;
  padding: 0;
  background-color: #111827;
}
.el-footer{
  background-color: #111827;
}
</style>
