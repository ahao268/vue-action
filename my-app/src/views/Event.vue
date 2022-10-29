<!-- 事件Demo -->
<template>
  <div>
    name: {{ name }}<br />
    <input type="text" @change="handleChange" />
  </div>
</template>

<script>
export default {
  props: {
    name: String,
  },
  methods: {
    handleChange(e) {
      this.$emit("changeName", e.target.value)
    },
  },
}
</script>

<style></style>
