<template>
  <div class="flag">
   <div class="title4"><h1>Country flag</h1></div>
    <div class="input2">
      <input
        type="text"
        v-model="text"
        placeholder="Shows your country"
        id="FlagSearch"
      /></div>
      <div class="search" v-on:click="isHidden=true"><button v-on:click="search()"><img src="../assets/checkbox.png" /> </button></div>
            <div class="imageBis" v-if="isHidden" ><img :src="image" /><br /></div>

      <div class="refresh2"  v-on:click="isHidden=false"><button @click="reload()"><img src="../assets/refresh.png" /></button></div>

    
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
  // methods: {
  //   async  search() {

  //         this.image = 'https://countryflagsapi.com/png/' + this.text

  //     }
  // }

  methods: {
    async search() {
      this.image = "https://countryflagsapi.com/png/" + this.text;
    },

    reload() {
      this.text = "";
      this.image = "";
    },
  },
};
</script>

<style lang="css">
.flag{
  display: flex;
  align-items: flex-end;
  flex-direction: column;
  background-color: #dbeca26b;
  min-height: 16em;
  width: 350px;
  height: 200px;
  margin: 30px;
  margin-top: 80px;
  border-radius: 10%;
}
.title4 h1 {
  position: relative;
  right: 125%;
  top: 50%;
  font-size: medium;
  font-weight: bolder;
}
.input2 input {
  position: relative;
  top: 35px;
  right: 47.5%;
  border: SOLID black;
  border-radius: 3%;
  background: #dbeca26b;
}
.search button {
  position: relative;
  right: 10%;
  top: 8%;
  cursor: pointer;
  border: none;
  background: none;
}

.search img {
  position: relative;
  height: 40px;
  width: 40px;
  right: 47px;
  top: -4px;
}

.refresh2 button {
  position: relative;
  right: 10%;
  top: 8%;
  cursor: pointer;
  border: none;
  background: none;
}
.refresh2 img {
  position: relative;
  height: 20px;
  width: 20px;
  right: 263px;
  bottom: 16px;
}
</style>