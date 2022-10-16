<template>
  <header>
    <div class="chuck">
      <!-- <h1>Chuck Norris</h1> -->
      <img
        class="card-img-top"
        src="../assets/chucknorris_logo.png"
        alt="Card image cap"
      />

      <div class="text-container">
        <!-- <button @click="update">Update</button> -->
        <p class="text">{{ chuck.value }}</p>
      </div>
    </div>
  </header>
</template>

<script>
import axios from "axios";
export default {
  name: "widgetOne",

  data() {
    return {
      chuck: [],
    };
  },

  methods: {
    chuckCall: function () {
      axios.get("https://api.chucknorris.io/jokes/random").then((response) => {
        this.chuck = response.data;
      });
    },

    refreshChuck: function () {
      setInterval(() => {
        this.chuckCall();
      }, 10000);
    },

    //     setTimeout(() => {
    //     axios.get('https://api.chucknorris.io/jokes/random').then((response) => {this.chuck = response.data;})
    //     console.log(setTimeout)
    // }, 10000)

    // function timedRefresh(timeoutPeriod) {
    // 	setTimeout("location.reload(true);",timeoutPeriod);
    // }

    // document.getElementbyId("header")= timedRefresh(5000);
  },
  mounted() {
    this.chuckCall();
    this.refreshChuck();
  },
};
</script>

<style lang="css">
.chuck {
  display: flex;
  align-items: flex-end;
  flex-direction: column;
  background-color: rgb(41, 171, 226);
  min-height: 16em;
  width: 350px;
  height: 150px;
  margin: 30px;
  margin-top: 80px;
  border-radius: 10%;
  align-items: center;
  align-content: center;
}
.chuck img {
  height: 120px;
  padding: 10px 10px 10px 10px;
}

.text-container {
  height: 6em;
  overflow-x: hidden; /* Hide horizontal scrollbar */
  overflow-y: auto; /* Add vertical scrollbar */
}
::-webkit-scrollbar {
  width: 5px;
}
</style>

