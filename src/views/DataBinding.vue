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
    <br />
    <img v-bind:src="imgSrc" />
    <br />
    <input type="text" v-model="textValue" />
    <button type="button" v-bind:disabled="textValue === ''">Click</button><br />
    <div
      class="container"
      v-bind:class="{
        active: isActive,
        'text-red': hasError,
      }">
      Class Binding
    </div>
    <div class="container" v-bind:class="[activeClass, errorClass]">Class Binding</div>
    <div v-bind:style="styleObject">인라인 스타일 바인딩</div>
    <table>
      <thead>
        <tr>
          <th>제품명</th>
          <th>가격</th>
          <th>카테고리</th>
          <th>배송료</th>
        </tr>
      </thead>
      <tbody>
        <tr :key="i" v-for="(product, i) in productList">
          <td>{{ product.product_name }}</td>
          <td>{{ product.price }}</td>
          <td>{{ product.category }}</td>
          <td>{{ product.delivery_price }}</td>
        </tr>
      </tbody>
    </table>
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
      imgSrc: "https://kr.vuejs.org/images/logo.png",
      textValue: "",
      isActive: true,
      hasError: false,
      activeClass: "active",
      errorClass: "text-red",
      styleObject: {
        color: "red",
        fontSize: "13px",
      },
      productList: [
        {
          product_name: "기계식키보드",
          price: 25000,
          category: "노트북/태블릿",
          delivery_price: 5000,
        },
        {
          product_name: "무선마우스",
          price: 12000,
          category: "노트북/태블릿",
          delivery_price: 5000,
        },
        {
          product_name: "아이패드",
          price: 725000,
          category: "노트북/태블릿",
          delivery_price: 5000,
        },
        {
          product_name: "무선충전기",
          price: 42000,
          category: "노트북/태블릿",
          delivery_price: 5000,
        },
        {
          product_name: "태블릿거치대",
          price: 32000,
          category: "노트북/태블릿",
          delivery_price: 5000,
        },
      ],
    };
  },
};
</script>

<style scoped>
container {
  width: 100%;
  height: 200px;
}
.active {
  background-color: yellow;
  font-weight: bold;
}
.text-red {
  color: red;
}
table {
  font-family: arial, sans-serif;
  border-collapse: collapse;
  width: 100%;
}
td,
th {
  border: 1px solid #dddddd;
  text-align: left;
  padding: 8px;
}
</style>
