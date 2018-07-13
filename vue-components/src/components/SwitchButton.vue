<template>
  <div :class="{container:true, active}">
    <div :class="{thumb:true, active}" @click="change"/>
  </div>
</template>

<script>
export default {
  props: ["value"],
  computed: {
    active() {
      return this.value
    }
  },

  methods: {
    change() {
      this.$emit("input", !this.value);
    }
  }
};
</script>

<style scoped>
.container {
  width: 40px;
  height: 24px;
  border: 1px solid #ccc;
  border-radius: 4px;
  cursor: pointer;
  background-color: #ddd;
}
.container.active {
  background-color: #20a8d8;
}
.thumb {
  width: 20px;
  height: 20px;
  margin: 1px;
  border: 1px solid #ccc;
  border-radius: 2px;
  background-color: #fff;
  transition: transform 0.2s;
}
.thumb.active {
  transform: translateX(16px);
}
</style>