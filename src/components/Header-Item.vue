<script setup>
import { ref } from 'vue'
import { useI18n } from 'vue-i18n'
const logo = '/GT工作室LOGO.png'

const { locale } = useI18n()
const currentLocale = ref(locale.value)

const changeLanguage = () => {
  locale.value = currentLocale.value
  localStorage.setItem('locale', currentLocale.value) // 存到本地，保持選擇
}
</script>

<template>
  <div class="header">
    <div class="header-title">
      <el-avatar
        :src="logo"
      />
      <span class="title-text">
        {{ $t('gt_title') }}
      </span>
    </div>

    <div class="header-menu">
      <el-anchor
        :offset="70"
        direction="horizontal"
        class="header-menu-anchor"
      >
        <el-anchor-link
          :href="`#`"
          class="header-memu-item"
        >
          {{ $t('home') }}
        </el-anchor-link>
        <el-anchor-link
          :href="`#1`"
          class="header-memu-item"
        >
          {{ $t('about') }}
        </el-anchor-link>
        <el-anchor-link
          :href="`#2`"
          class="header-memu-item"
        >
          {{ $t('services') }}
        </el-anchor-link>
        <el-anchor-link
          :href="`#3`"
          class="header-memu-item"
        >
          {{ $t('contact') }}
        </el-anchor-link>
      </el-anchor>
      <div class="language">
        <el-select
          v-model="currentLocale"
          class="language-select"
          @change="changeLanguage"
        >
          <el-option
            value="zh-TW"
            label="繁體中文"
          />
          <el-option
            value="en"
            label="English"
          />
        </el-select>
      </div>
    </div>
  </div>
</template>

<style scoped>
.header{
  display: flex;
  justify-content: space-between;
  background-color: #111827;
  border: #1F2937 1px solid;
  height: 60px;
}
.header-title{
  margin-left: 50px;
  display: flex;
  align-items: center;
}
.title-text{
  font-family: 'Noto Sans TC';
  font-size: 20px;
  color:#ffffff;
  margin-left: 5px;
}
.header-menu{
  display: flex;
  align-items: center;
  margin-right: 50px;
}
.header-menu-anchor{
  background-color: #111827;
}
:deep(.header-memu-item > .el-anchor__link){
  color: #ffffff;
  font-size: 16px;
  font-family: 'Noto Sans TC';
}
.language{
  margin-left: 16px;
  padding: 6px;
  width: 120px;
}
:deep(.language-select > .el-select__wrapper){
  background-color: initial;
  color: #ffffff;
}
:deep(.language-select > .el-select__wrapper > .el-select__selection > .el-select__placeholder > span){
  color: #ffffff;
}
</style>
