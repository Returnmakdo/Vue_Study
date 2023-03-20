<template>
  <div class="about">
    <h1>This is binding page</h1>
    <h3>{{ data }}</h3>
    <p v-html="htmlString"></p>
    <input type="text" v-model="valueModel" /><br />
    <textarea v-model="message"></textarea><br />
    <select v-model="city">
      <option value="02">서울</option>
      <option value="21">부산</option>
      <option value="064">제주</option>
    </select>
    <br />
    <label><input type="checkbox" v-model="checked" value="서울" />서울</label>
    <label><input type="checkbox" v-model="checked" value="부산" />부산</label>
    <label><input type="checkbox" v-model="checked" value="제주" />제주</label>
    <br />
    <span>체크한 지역 : {{ checked }}</span>
    <br />
    <label><input type="radio" v-model="picked" v-bind:value="radioVaule1" />서울</label>
    <label><input type="radio" v-model="picked" v-bind:value="radioVaule2" />부산</label>
    <label><input type="radio" v-model="picked" v-bind:value="radioVaule3" />제주</label>
    <br />
    <span>체크한 지역 : {{ picked }}</span>
  </div>
</template>

<script>
export default {
  data() {
    return {
      data: "hello, data",
      htmlString: '<p style="color:red;">This is a html string</p>',
      valueModel: "Chi Young",
      message: "this is textarea",
      city: "02",
      checked: [],
      picked: "",
      radioVaule1: "서울",
      radioVaule2: "부산",
      radioVaule3: "제주",
    };
  },
};
</script>
