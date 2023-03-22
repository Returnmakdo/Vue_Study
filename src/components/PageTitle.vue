<template>
  <h2>{{ msg }}</h2>
  <button type="button" @click="childFunc" ref="btn">Click</button>
</template>

<script>
export default {
  data() {
    return {
      msg: "자슥에서 부모로",
    };
  },
  methods: {
    callFromParent() {
      console.log("부모 컴포넌트에서 직접 호출한 함수");
    },
  },
  props: {},
  mounted() {
    this.$emit("send-message", this.msg);
  },
};
</script>
