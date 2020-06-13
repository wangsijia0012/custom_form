# 最精简的通过接口生成表单案例，直接运行，代码易懂，结构简练

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev


##获取表单参数的接口数据
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




