<template>
  <div class="cat2">
    <div class="Title"><h1>Find your type of cat</h1></div>
      <div class="input6">
      <input
        type="text"
        v-model="text"
        placeholder="Search"
        id="textCat"
      /></div>
      <div class="doneBis" v-on:click="isHidden=true">
      <button v-on:click="Cat()"><img src="../assets/checkbox.png" /></button
      ><br />
    </div>
    <div class="imageBis" v-if="isHidden"><img :src="image" /><br/></div>

<div class="refreshBis"  v-on:click="isHidden=false">
  <button @click="reload()"><img src="../assets/refresh.png" /></button
  ><br />
  </div>
  </div>
</template>

<script>
export default {
  name: "widgetOne",

  data() {
    return {
      text: "",
      image: "",
      isHidden: false,  
    };
  },
  methods: {
    Cat() {
      this.image = "https://cataas.com/cat/" + this.text;
    },
    reload() {
      this.text = "";
      this.image = "";
    },
  },
};
</script>

<style lang="css">
.cat2 {
  display: flex;
  align-items: flex-end;
  flex-direction: column;
  background-color: #e7969d4c;
  min-height: 16em;
  width: 350px;
  height: 200px;
  margin: 30px;
  margin-top: 80px;
  border-radius: 10%;
}

.cat2 img {
  position: relative;
  height: 120px;
}

.Title h1 {
  position: relative;
  right: 60%;
  top: 50%;
  font-size: medium;
  font-weight: bolder;
}

.input6 input {
  position: relative;
  top: 35px;
  right: 47.5%;
  border: SOLID black;
  border-radius: 3%;
  background: #e7969d4c;
}

.doneBis button {
  position: relative;
  right: 10%;
  top: 8%;
  cursor: pointer;
  border: none;
  background: none;
}

.doneBis img {
  position: relative;
  height: 40px;
  width: 40px;
  right: 45px;
  top: -4px;
}
.refreshBis button {
  position: relative;
  right: 10%;
  top: 8%;
  cursor: pointer;
  border: none;
  background: none;
}
.refreshBis img {
  position: relative;
  height: 20px;
  width: 20px;
  right: 263px;
  bottom: 16px;
}

.imageBis img {
  position: relative;
  width: 200px;
  height: 130px;
  top: 10px;
  right: 70px;
  border: none;
}
</style>