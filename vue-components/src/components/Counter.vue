<template>
  <div class="ct">
    <label>{{count}}</label>
    <button @click="addcount">加1</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      count: 0
    };
  },
  methods: {
    addcount() {
      this.count += 1;
    }
  }
};
</script>

