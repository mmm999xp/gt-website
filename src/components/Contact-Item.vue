<script setup>
import { reactive, ref, computed } from 'vue'
import { useI18n } from 'vue-i18n'

const { t } = useI18n()
const formSize = ref('default')
const ruleFormRef = ref()
const ruleForm = reactive({
  name: '',
  telephone: '',
  email: '',
  preDeadline: '',
  desc: '',
  Personal_Information_Check: []
})

const rules = computed(() => ({
  name: [
    { required: true, message: () => t('contact_form_name_verify1'), trigger: 'change' },
    { min: 1, max: 8, message: () => t('contact_form_name_verify2'), trigger: 'change' }
  ],
  telephone: [
    { min: 10, max: 10, message: () => t('contact_form_telephone_verify1'), trigger: 'change' }
  ],
  email: [
    { required: true, message: () => t('contact_form_email_verify1'), trigger: 'change' },
    {
      pattern: /^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$/,
      message: () => t('contact_form_email_verify2'),
      trigger: 'blur'
    }
  ],
  preDeadline: [
    { required: true, message: () => t('contact_form_preDeadline_verify1'), trigger: 'change' }
  ],
  desc: [
    { required: true, message: () => t('contact_form_desc_verify1'), trigger: 'blur' }
  ]
}))

const submitForm = async formEl => {
  if (!formEl) return
  await formEl.validate((valid, fields) => {
    if (valid) {
      console.log('submit!')
    } else {
      console.log('error submit!', fields)
    }
  })
}

const resetForm = formEl => {
  if (!formEl) return
  formEl.resetFields()
}

</script>

<template>
  <div class="contact">
    <div class="contact-title">
      {{ $t('contact_title') }}
    </div>
    <el-form
      ref="ruleFormRef"
      :model="ruleForm"
      :rules="rules"
      label-width="auto"
      class="form"
      :size="formSize"
      status-icon
      label-position="top"
    >
      <el-form-item
        :label="$t('contact_form_name')"
        prop="name"
      >
        <el-input
          v-model="ruleForm.name"
          :placeholder="$t('contact_form_name_placeholder')"
          autocomplete="off"
        />
      </el-form-item>
      <el-form-item
        :label="$t('contact_form_telephone')"
        prop="telephone"
      >
        <el-input
          v-model="ruleForm.telephone"
          :placeholder="$t('contact_form_telephone_placeholder')"
        />
      </el-form-item>
      <el-form-item
        :label="$t('contact_form_email')"
        prop="email"
      >
        <el-input
          v-model="ruleForm.email"
          :placeholder="$t('contact_form_email_placeholder')"
        />
      </el-form-item>
      <el-form-item
        :label="$t('contact_form_preDeadline')"
        prop="preDeadline"
      >
        <el-select
          v-model="ruleForm.preDeadline"
          :placeholder="$t('contact_form_preDeadline_placeholder')"
        >
          <el-option
            :label="$t('contact_form_preDeadline_select_item1')"
            value="The sooner the better"
          />
          <el-option
            :label="$t('contact_form_preDeadline_select_item2')"
            value="Within 7 days"
          />
          <el-option
            :label="$t('contact_form_preDeadline_select_item3')"
            value="Within 14 days"
          />
          <el-option
            :label="$t('contact_form_preDeadline_select_item4')"
            value="Within 30 days"
          />
          <el-option
            :label="$t('contact_form_preDeadline_select_item5')"
            value="To be discussed later"
          />
        </el-select>
      </el-form-item>

      <el-form-item
        :label="$t('contact_form_desc')"
        prop="desc"
      >
        <el-input
          v-model="ruleForm.desc"
          type="textarea"
          :autosize="{ minRows: 4, maxRows: 12 }"
          :placeholder="$t('contact_form_desc_placeholder')"
        />
      </el-form-item>
      <el-form-item
        label=""
      >
        <el-checkbox-group v-model="ruleForm.Personal_Information_Check">
          <el-checkbox
            value="Personal_Information_Check"
            name="Personal_Information_Check"
          >
            {{ $t('contact_form_personal_information_check') }}
          </el-checkbox>
        </el-checkbox-group>
      </el-form-item>
      <el-form-item>
        <el-button
          type="primary"
          :disabled="ruleForm.Personal_Information_Check.length === 0"
          @click="submitForm(ruleFormRef)"
        >
          {{ $t('contact_form_submit') }}
        </el-button>
        <el-button @click="resetForm(ruleFormRef)">
          {{ $t('contact_form_reset') }}
        </el-button>
      </el-form-item>
    </el-form>
  </div>
</template>

<style scoped>
.contact{
  width: 100%;
  min-height: 800px;
  background-color: #1F2937;
  padding-bottom: 16px;
  display: flex;
  flex-direction: column;
  align-items: center;
  font-family: 'Space Grotesk' , 'Noto Sans TC';
}
.contact-title{
  color: #ffffff;
  font-family: 'Noto Sans TC';
  font-size: 30px;
  display: flex;
  justify-content: center;
  padding: 50px 0;
}
.form{
  max-width: 92vw;
}
:deep(.el-form-item__label){
  color: #ffffff;
}
:deep(.el-input__wrapper){
  background: #111827;
  height: 40px;
  box-shadow:0 0 0 1px #374151;
}
:deep(.el-textarea__inner){
  background: #111827;
  box-shadow:0 0 0 1px #374151;
}
:deep(.el-select__wrapper){
  background: #111827;
  height: 40px;
  box-shadow:0 0 0 1px #374151;
}
:deep(.el-select__selected-item){
  color: #ffffff;
}
:deep(.el-input__inner){
  color: #ffffff;
}
:deep(.el-textarea__inner){
  color: #ffffff;
}
:deep(.el-checkbox__label){
  color: #9CA3AF;
  max-width: 520px;
}
:deep(.el-checkbox){
  margin:  20px 0;
}
:deep(.is-focus){
  box-shadow:0 0 0 1px #0046b8;
}
.el-checkbox{
  white-space: normal;
}
</style>
<style>
.el-scrollbar{
  background-color: #111827;
}
.el-select-dropdown__item > span {
  color: #ffffff;
}
.el-select-dropdown__item.is-hovering{
  background-color: #374151 ;
}
</style>
