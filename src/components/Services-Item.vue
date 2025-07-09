<script setup>
import { Right } from '@element-plus/icons-vue'
</script>

<template>
  <div class="service">
    <div class="service-title">
      {{ $t('service_title') }}
    </div>
    <div class="service-group">
      <div class="service-item">
        <img
          src="/網站開發.png"
          class="service-icon"
        >
        <div class="service-item-title">
          {{ $t('service_item_title1') }}
        </div>
        <div class="service-item-text">
          {{ $t('service_item_text1') }}
        </div>
        <div class="service-item-button">
          {{ $t('service_item_button') }}
          <el-icon><Right /></el-icon>
        </div>
      </div>
      <div class="service-item">
        <img
          src="/企業平台.png"
          class="service-icon"
        >
        <div class="service-item-title">
          {{ $t('service_item_title2') }}
        </div>
        <div class="service-item-text">
          {{ $t('service_item_text2') }}
        </div>
        <div class="service-item-button">
          {{ $t('service_item_button') }}
          <el-icon><Right /></el-icon>
        </div>
      </div>
      <div class="service-item">
        <img
          src="/行動應用.png"
          class="service-icon"
        >
        <div class="service-item-title">
          {{ $t('service_item_title3') }}
        </div>
        <div class="service-item-text">
          {{ $t('service_item_text3') }}
        </div>
        <div class="service-item-button">
          {{ $t('service_item_button') }}
          <el-icon><Right /></el-icon>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.service{
  width: 100%;
  min-height: 360px;
  padding-bottom: 16px;
}
.service-title{
  color: #ffffff;
  font-family: 'Noto Sans TC';
  font-size: 30px;
  display: flex;
  justify-content: center;
  padding: 50px 0;
}
.service-group{
  display: flex;
  justify-content: space-evenly;
  flex-wrap: wrap;
  width: 100%;
}
.service-item{
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  background-color: #1F2937;
  border-radius: 12px;
  width: 25%;
  min-width: 240px;
  max-width: 375px;
  min-height: 1.2rem;
  outline: #374151 1px solid;
  padding: 24px;
  margin: 16px;
}
/* .service-item:hover{
  outline: #0046b8 2px solid;
} */
.service-item-title{
  color: #ffffff;
  font-family: 'Noto Sans TC';
  font-size: 20px;
  margin-bottom: 16px;
}
.service-item-text{
  color: #9CA3AF;
  font-family: 'Noto Sans TC';
  font-size: 16px;
}
.service-icon{
  height: 50px;
  width: 55px;
}
.service-item-button{
  display: flex;
  align-items: center;
  color: #60A5FA;
  margin-top: 16px;
  font-family: 'Noto Sans TC' ,'Syne';
}
.service-item-button:hover{
  font-weight: bold;
  cursor: pointer;
}

.el-icon{
  margin-left: 5px;
  padding-top: 3px;
  font-size: 16px;
}

</style>
