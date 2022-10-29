<!-- 使用一些组件 -->
<template>
  <div>
    <!-- <Props :type="type" :is-visible="false" :onChange="handleProChange"></Props> -->
    <Event :name="name" @changeName="changeName"></Event>
  </div>
</template>

<script>
// import Props from "./Props.vue"
import Event from "./Event.vue"
export default {
  data() {
    return {
      type: "success",
      name: "hello",
    }
  },
  components: {
    // Props,
    Event,
  },
  methods: {
    handleProChange() {},
    changeName(e) {
      this.name = e
    },
  },
}
</script>

<style></style>
