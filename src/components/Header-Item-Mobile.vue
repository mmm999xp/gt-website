<script setup>
import { ref } from 'vue'
import { useI18n } from 'vue-i18n'
const MenuIcon = '/menu.png'
const logo = '/GT工作室LOGO.png'

const closeDropdown = () => {
  document.body.click() // 手動觸發 Element Plus 下拉選單關閉
}
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
      <el-dropdown
        trigger="click"
        popper-class="menu-dropdown"
      >
        <img
          :src="MenuIcon"
          class="dropdown-icon"
        >
        <template #dropdown>
          <el-dropdown-menu>
            <el-anchor
              direction="vertical"
              class="dropdown-anchor"
            >
              <el-anchor-link
                href="#home"
                @click="closeDropdown"
              >
                {{ $t('home') }}
              </el-anchor-link>
              <el-anchor-link
                href="#about"
                @click="closeDropdown"
              >
                {{ $t('about') }}
              </el-anchor-link>
              <el-anchor-link
                href="#services"
                @click="closeDropdown"
              >
                {{ $t('services') }}
              </el-anchor-link>
              <el-anchor-link
                href="#3"
                @click="closeDropdown"
              >
                {{ $t('contact') }}
              </el-anchor-link>
            </el-anchor>
          </el-dropdown-menu>
        </template>
      </el-dropdown>
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
  margin-left: 5px;
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
  margin-right: 16px;
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
.dropdown-icon {
  width: 40px;
  height: 40px;
  cursor: pointer;
}

</style>
<style>
.menu-dropdown{
  min-width: 200px;
  padding: 10px;
}
.dropdown-anchor{
  background-color: #111827;
}
 .dropdown-anchor > .el-anchor__list > .el-anchor__item > .el-anchor__link{
  min-width: 200px;
  padding: 10px;
  font-size: 16px;
  font-weight: 600;
  color: #ffffff;
}
.dropdown-anchor > .el-anchor__list > .el-anchor__item > .is-active{
color: #409EFF;
}
.el-dropdown-menu{
  padding: 0;
}
</style>
