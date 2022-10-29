<!-- 组件属性的写法 -->
<template>
  <div>
    type: {{ type }} <br />
    isVisible: {{ isVisible }} <br />
    <button @click="handleClick">点击</button>
  </div>
</template>

<script>
export default {
  //inheritAttrs: false,//默认属性是否挂载到组件根元素
  props: {
    name: String,
    type: {
      validator: function (value) {
        //类型校验
        let types = ["success", "fail"] //是否是这其中的类型
        return types.includes(value)
      },
    },
    list: {
      type: Array,
      default: () => [],
    },
    isVisible: {
      type: Boolean,
      default: false,
    },
    onChange: {
      //一般不取这个名字
      type: Function,
      default: () => {},
    },
  },
  methods: {
    handleClick() {
      //想更改父组件的属性，不能像这样写
      //this.type = "warning"
      //还可以的方式，但不是最好
      //this.onChange("warning")
    },
  },
}
</script>

<style></style>
