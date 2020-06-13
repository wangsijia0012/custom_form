<template>
  <div>
    <CustomForm
      ref="CustomForm"
      :formConfig="formConfig"
      :formParam="formParam"
      @flushData="flushData"
      @vilidated="vilidated"
    />
    <el-button
      @click="submit"
      type="primary"
    >submit</el-button>
  </div>
</template>

<script>
import CustomForm from '@/components/CustomForm'
export default {
  name: 'CustomFormDemo',
  components: { CustomForm },
  data() {
    return {
      // 要提交表单的数据结构（通过接口获取）
      formParam: {
        name: '',
        gender: ''
      },
      // 表单的配置（通过接口获取）
      formConfig: {
        inline: false,
        labelPosition: 'top',
        labelWidth: '',
        size: 'small',
        statusIcon: true,
        className: 'custom-form1',
        style: '',
        formItemList: [
          {
            type: 'input',
            label: '姓名',
            disable: false,
            readonly: false,
            value: '',
            placeholder: '请输入姓名',
            rules: [
              { required: true, message: '请输入活动名称', trigger: 'blur' }
            ],
            key: 'name',
            subtype: "text",
            className: 'custom1',
            style: ''
          },
          {
            type: "select",
            label: "性别",
            value: "",
            button: false,
            border: true,
            rules: [],
            key: "gender",
            className: 'custom1',
            style: '',
            options: [
              {
                value: '1',
                label: '男',
                disabled: false
              },
              {
                value: "0",
                label: "女",
                disabled: false
              }
            ]
          }
        ]
      }
    }
  },
  mounted() {
    //获取表单参数以及表单配置
  },
  methods: {
    flushData(formData) {
      this.formParam = formData
    },
    vilidated() {
      //校验表单后需要执行的提交等逻辑
      alert(JSON.stringify(this.formParam))
    },
    submit() {
      this.$refs.CustomForm.submitForm()
    }
  }
}
</script>

<style scoped>
</style>
