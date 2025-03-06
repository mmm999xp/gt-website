<script setup>
const logo = '/GT工作室LOGO.png'
</script>

<template>
  <div class="footer">
    <div class="footer-title">
      <el-avatar
        :src="logo"
      />
      <span class="title-text">
        {{ $t('gt_title') }}
      </span>
    </div>
    <div class="footer-main">
      {{ $t('footer_main') }}
    </div>
    <div class="footer-link">
      <div class="contact-link">
        <el-link
          href="https://www.facebook.com/share/1B5AnLDTem/?mibextid=LQQJ4d"
          target="_blank"
          :underline="false"
        >
          <img src="/facebook.png">
        </el-link>
      </div>
    </div>
  </div>
</template>

<style scoped>
.footer{
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: 100%;
}
.footer-title{
  display: flex;
  align-items: center;
}
.title-text{
  font-size: 20px;
  font-family: 'Noto Sans TC' , 'Space Grotesk';
  color:#ffffff;
  margin-left: 6px;
}
.footer-main{
  font-family: 'Noto Sans TC' , 'Space Grotesk';
  font-size: 14px;
  color: #9CA3AF;
}
.contact-link:hover  {
  background-color: blue;
  border-radius: 50%;
}
</style>
