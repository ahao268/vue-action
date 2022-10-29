<!-- 双向绑定demo -->
<template>
  <div>
    <input
      type="number"
      :value="phoneInfo.phone"
      @change="handlePhoneChange"
    />
  </div>
</template>

<script>
export default {
  model: {
    prop: "phoneInfo",
    event: "change",
  },
  props: {
    phoneInfo: Object,
  },
  methods: {
    handlePhoneChange(e) {
      if (e.target.value === "") {
        console.log("不能为空")
      }
      this.$emit("change", {
        ...this.phoneInfo,
        phone: e.target.value,
      })
    },
  },
}
</script>

<style></style>
