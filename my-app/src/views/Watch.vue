<!--  -->
<template>
  <div>
    <input type="text" v-model="changeName" /><br />
    {{ fullName }}
  </div>
</template>

<script>
export default {
  data() {
    return {
      fullName: "",
      changeName: "",
      timer: 0,
    }
  },
  watch: {
    changeName(value) {
      //这里是防抖，不然的话用户每输入一个字符都执行了一次，
      //而防抖可以在用户输入完一段时间才执行一次
      if (this.timer === 0) {
        this.timer = setTimeout(() => {
          //更新数据
          this.fullName = value
        }, 2000)
      } else {
        clearTimeout(this.timer)
        this.timer = setTimeout(() => {
          //更新数据
          this.fullName = value
        }, 2000)
      }
    },
  },
}
</script>

<style></style>
