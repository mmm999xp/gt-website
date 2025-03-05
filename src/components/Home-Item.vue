<script setup>

</script>

<template>
  <div class="hero-section">
    <div class="hero-content">
      <h1>{{ $t('banner_title') }} <div class="highlight">{{ $t('banner_title_highlight') }}</div></h1>
      <p>{{ $t('banner_text') }}</p>
      <div class="buttons">
        <el-button type="primary">
          {{ $t('banner_button') }}
        </el-button>
      </div>
    </div>
  </div>
</template>

<style scoped>
.hero-section {
  position: relative;
  width: 100%;
  height: 700px; /* 全螢幕 */
  background: url('/banner2.png') no-repeat center center/cover;
  display: flex;
  align-items: center;
  justify-content: flex-start;
  text-align: left;
}

.hero-content {
  max-width: 600px;
  margin-left: 5%;
  font-family: 'Syne', 'Noto Sans TC';
  color: #ffffff;
}

h1 {
  font-size: 64px;
  font-weight: 400;
}

.highlight {
  color: #3b82f6; /* 藍色 */
}

p {
  font-size: 20px;
  margin-bottom: 20px;
  color: #9CA3AF;
}

.buttons {
  display: flex;
  gap: 10px;
}
/* 在 .hero-section 加一個半透明背景層 */
.hero-section::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: black; /* 背景遮罩顏色 */
  opacity: 0.5; /* 不透明度 */
  z-index: 1;
}

/* 內容在遮罩上層 */
.hero-content {
  position: relative;
  z-index: 2;
}
</style>
