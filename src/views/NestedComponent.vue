import PageTitle from '@/components/PageTitle.vue';

<template>
  <div>
    <PageTitle @send-message="sendMessage" ref="child_component" title="전달된 props" />
    <button type="button" @click="changeChildData">gkdl</button>
  </div>
</template>

<script>
import PageTitle from "../components/PageTitle.vue";
export default {
  components: { PageTitle },
  mounted() {
    this.$refs.child_component.callFromParent();
  },
  methods: {
    sendMessage(data) {
      console.log(data);
    },
    changeChildData() {
      this.$refs.child_component.msg = "부모의 데이터";
    },
  },
};
</script>
