<script setup>

</script>

<template>
  <div class="about">
    <div class="about-title">
      {{ $t('about_title') }}
    </div>
    <div class="about-group">
      <div class="about-item">
        <img
          src="/我們的使命.png"
          class="about-icon"
        >
        <div class="about-item-title">
          {{ $t('about_item_title1') }}
        </div>
        <div class="about-item-text">
          {{ $t('about_item_text1') }}
        </div>
      </div>
      <div class="about-item">
        <img
          src="/核心價值.png"
          class="about-icon"
        >
        <div class="about-item-title">
          {{ $t('about_item_title2') }}
        </div>
        <div class="about-item-text">
          {{ $t('about_item_text2') }}
        </div>
      </div>
      <div class="about-item">
        <img
          src="/專業技術.png"
          class="about-icon"
        >
        <div class="about-item-title">
          {{ $t('about_item_title3') }}
        </div>
        <div class="about-item-text">
          {{ $t('about_item_text3') }}
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.about{
  width: 100%;
  min-height: 360px;
  background-color: #1F2937;
  padding-bottom: 16px;
}
.about-title{
  color: #ffffff;
  font-family: 'Noto Sans TC';
  font-size: 30px;
  display: flex;
  justify-content: center;
  padding: 50px 0;
}
.about-group{
  display: flex;
  justify-content: space-evenly;
  flex-wrap: wrap;
}
.about-item{
  background-color: #111827;
  border-radius: 12px;
  width: 25%;
  min-width: 300px;
  max-width: 450px;
  outline: #374151 1px solid;
  padding: 24px;
  margin: 16px;
}
.about-item:hover{
  outline: #0046b8 2px solid;
}
.about-item-title{
  color: #ffffff;
  font-family: 'Noto Sans TC';
  font-size: 20px;
  margin-bottom: 16px;
}
.about-item-text{
  color: #9CA3AF;
  font-family: 'Noto Sans TC';
  font-size: 16px;
}
.about-icon{
  height: 40px;
  width: 32px;
}
</style>
