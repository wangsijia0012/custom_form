<template>
  <el-form
    ref="form"
    :class="formConfig.className"
    :style="formConfig.style"
    :inline="formConfig.inline"
    :model="formParam"
    :label-position="formConfig.labelPosition"
    :label-width="formConfig.labelWidth"
    :size='formConfig.size'
    :status-icon="formConfig.statusIcon"
  >
    <customFormItem
      v-for="item in formConfig.formItemList"
      :key="item.key"
      v-if="formParam[item.key]!==undefined"
      :item="item"
      :value="formParam[item.key]"
      @input="handleInput($event, item.key)"
    />
  </el-form>

</template>

<script>
import CustomFormItem from "./CustomFormItem";
export default {
  name: 'CustomForm',
  props: {
    formConfig: {
      type: Object,
      required: true
    },
    formParam: {
      type: Object,
      required: true
    }
  },
  components: { CustomFormItem },
  methods: {
    handleInput(val, key) {
      this.$emit('flushData', { ...this.formParam, [key]: val })
    },
    setDefaultValue() {
      const formData = { ...this.value }
      this.formConfig.formItemList.forEach(({ key, value }) => {
        if (formData[key] === undefined || formData[key] === null) {
          formData[key] = value
        }
      })
      this.$emit('flushData', formData)
    },
    submitForm() {
      this.$refs['form'].validate((valid) => {
        if (valid) {
          this.$emit('vilidated')
        }
      })
    }
  },
  mounted() {
    this.setDefaultValue()
  }
}
</script>

<style scope>
/* 表单样式 */
.custom-form1 {
  display: flex;
}
</style>
