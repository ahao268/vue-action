<!-- 使用一些组件 -->
<template>
  <div>
    <!-- <Props :type="type" :is-visible="false" :onChange="handleProChange"></Props> -->
    <!-- <Event :name="name" @changeName="changeName"></Event> -->
    <PersonalInfo v-model="phoneInfo"></PersonalInfo>
    <PersonalInfo
      :phone-info="phoneInfo"
      @change="(val) => (phoneInfo = val)"
    ></PersonalInfo>
    phoneInfo: {{ phoneInfo }}
  </div>
</template>

<script>
// import Props from "./Props.vue"
// import Event from "./Event.vue"
import PersonalInfo from "./PersonalInfo.vue"
export default {
  data() {
    return {
      type: "success",
      name: "hello",
      phoneInfo: {
        areaCode: "+86",
        phone: "",
      },
    }
  },
  components: {
    // Props,
    // Event,
    PersonalInfo,
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
