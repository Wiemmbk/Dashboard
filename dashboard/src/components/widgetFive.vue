<template>
  <div class="logo">
    <div class="title5">
    <h1>Make YOUR logo</h1></div>
    <div>
      <div class="input2">
      <input
        type="text"
        v-model="text"
        placeholder="Your letters"
        id="letterSearch"
      /></div>
      <div class="done" v-on:click="isHidden=true">
        <button v-on:click="search()">
          <img src="../assets/search.png" />
        </button>
      </div>
      <div class="image" v-if="isHidden"><img :src="image" /></div>
      <div class="refresh3"  v-on:click="isHidden=false">
        <button @click="reload()"><img src="../assets/refresh.png" /></button><br />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "widgetFour",

  data() {
    return {
      text: "",
      image: "",
      isHidden: false,  
    };
  },
  methods: {
    async search() {
      this.image =
        "https://avatars.dicebear.com/api/initials/" + this.text + ".svg";
    },
    reload() {
      this.text = "";
      this.image = "";
    },
  },
};
</script>

<style lang="css">
.logo {
  display: flex;
  align-items: flex-end;
  flex-direction: column;
  background-color: #4ce0a027;
  min-height: 16em;
  width: 350px;
  height: 200px;
  margin: 30px;
  margin-top: 80px;
  border-radius: 10%;
}
.title5 h1 {
  position: relative;
  right: 83%;
  top: 50%;
  font-size: medium;
  font-weight: bolder;
}
.input2 input {
  position: relative;
  top: 35px;
  right: 48.5%;
  border: SOLID black;
  border-radius: 3%;
  background: #4ce0a027;
}

.done button {
  position: relative;
  right: 10%;
  top: 8%;
  cursor: pointer;
  border: none;
  background: none;
}

.done img {
  position: relative;
  height: 30px;
  width: 30px;
 left: 36.5px;
  top: 3.5px;
  border: solid black;
}
.refresh3 button {
  position: relative;
  right: 10%;
  top: 28%;
  cursor: pointer;
  border: none;
  background: none;
}
.refresh3 img {
  position: relative;
  height: 20px;
  width: 20px;
  right: 150px;
  bottom: 5px;
}

.image img {
  position: relative;
  width: 150px;
  height: 150px;
  top: 10px;
  right: 80px;
  border: none;
}

</style>