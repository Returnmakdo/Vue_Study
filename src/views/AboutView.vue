<template>
  <div class="about">
    <h1>이벤트 처리</h1>
    <h1 v-if="bRender">bRender가 true면 이게 화면에 보임</h1>
    <h1 v-else>bRender가 false면 이게 화면에 보임</h1>
    <h1 v-if="type === 'A'">A</h1>
    <h1 v-else-if="type === 'B'">B</h1>
    <h1 v-else>C</h1>
    <h1 v-show="bShow">bShow가 true면 이 블록이 화면에 보임</h1>
    <button type="button" @click="increaseCounter">Add 1</button>
    <p>현재 수 : {{ counter }}</p>
    <button type="button" @click="setCount(7)">Add 1</button>
    <p>현재 수 : {{ counter }}</p>
    <select v-model="selectedValue" @change="changeSelect">
      <option value="서울">서울</option>
      <option value="부산">부산</option>
      <option value="제주">제주</option>
    </select>
    <h1>Full Name : {{ fullName }}</h1>
    <h1>My Name : {{ myName }}</h1>
    <button type="button" @click="changeName">내 이름 나와라</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      type: "B",
      bShow: true,
      counter: 0,
      selectedValue: "",
      firstName: "Chiyoung",
      lastName: "Ahn",
      myName: "",
    };
  },
  methods: {
    increaseCounter() {
      this.counter = this.counter + 1;
    },
    setCount(counter) {
      this.counter = counter;
    },
    changeSelect() {
      alert(this.selectedValue);
    },
    changeName() {
      this.firstName = "ChiChi";
    },
  },
  computed: {
    fullName() {
      return this.firstName + " " + this.lastName;
    },
  },
  watch: {
    firstName() {
      this.myName = this.firstName + " " + this.lastName;
    },
    lastName() {
      this.myName = this.firstName + " " + this.lastName;
    },
  },
};
</script>
