<template>
  <div class="chuck3">
    <div class="title2">
      <h1>Choose your excuse</h1>
    </div>
    <div class="select">
      <select v-model="result1">
        <option selected>Select</option>
        <option value="family">Family</option>
        <option value="office">Office</option>
        <option value="children">Children</option>
        <option value="college">College</option>
        <option value="party">Party</option>
      </select>
    </div>
    <div class="try">
      <button v-on:click="test()"><img src="../assets/search.png" /></button>
    </div>
    <div class="refreshf">
      <button @click="reload()"><img src="../assets/refresh.png" /></button
      ><br />
    </div>
    <div class="result">
      <p>{{ result }}</p>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "widgetThree",

  data() {
    return {
      result: "",
    };
  },
  methods: {
    test() {
      axios
        .get("https://excuser.herokuapp.com/v1/excuse/" + this.result)
        .then((response) => {
          this.result = response.data[0].excuse;
        });
    },
    reload() {
      this.result = "";
    },
  },
};
</script>

<style lang="css">
.chuck3 {
  display: flex;
  align-items: flex-end;
  flex-direction: column;
  background-color: #97c7b986;
  min-height: 16em;
  width: 350px;
  height: 200px;
  margin: 30px;
  margin-top: 80px;
  border-radius: 10%;
}
.title2 h1 {
  position: relative;
  right: 69%;
  top: 50%;
  font-size: medium;
  font-weight: bolder;
}
.select select {
  position: relative;
  top: 100%;
  right: 180%;
  border: solid black;
  background-color: #97c7b986;
}

.result p {
  display: flex;
  align-content: center;
  align-items: center;
  right: 10px;
}

.try button {
  position: relative;
  right: 10%;
  top: 8%;
  cursor: pointer;
  border: none;
  background: none;
}

.try img {
  position: relative;
  height: 26.8px;
  width: 26.8px;
  right: 117px;
  top: -4.5px;
  border: solid black;
}
.refreshf button {
  position: relative;
  right: 10%;
  top: 8%;
  cursor: pointer;
  border: none;
  background: none;
}
.refreshf img {
  position: relative;
  height: 20px;
  width: 20px;
  left: -300px;
  top: 120px;
}
</style>
