<template>
  <el-form-item
    :rules="item.rules"
    :label="item.label"
    :prop="item.key"
    :class="item.className"
    :style="item.style"
  >
    <el-input
      v-if="item.type==='input'"
      v-bind="$attrs"
      v-on="$listeners"
      :type="item.subtype"
      :placeholder="item.placeholder"
      :disabled="item.disable"
      :readonly="item.readonly"
      :autosize="item.autosize"
    ></el-input>

    <el-select
      v-else-if="item.type==='select'"
      v-bind="$attrs"
      v-on="$listeners"
      :multiple="item.multiple"
      :disabled="item.disabled"
      :multiple-limit="item.multipleLimit"
    >
      <el-option
        v-for="o in item.options"
        :key="o.value"
        :label="o.label"
        :value="o.value"
        :disabled="o.disabled"
      >
      </el-option>
    </el-select>
  </el-form-item>
</template>
<script>
export default {
  name: 'CustomFormItem',
  props: {
    item: {
      type: Object,
      required: true
    }
  }
}
</script>

<style scoped>
/* el-form-item 样式 */
.custom1 {
  width: 80px;
}
</style>
