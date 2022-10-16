<template>
  <body>
    <meta
      name="viewport"
      content="width=device-width, initial-scale=1, shrink-to-fit=no"
    />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <!-- NAV BAR -->

    <nav class="navbar fixed-top navbar-light bg-light">
      <a class="navbar-brand" href="#">DASHBOARD</a>

      <div class="dropdown">
        <button
          class="btn btn-secondary dropdown-toggle"
          type="button"
          id="dropdownMenuButton"
          data-toggle="dropdown"
          aria-haspopup="true"
          aria-expanded="false"
        >
          New Widget
        </button>
        <div class="dropdown-menu" aria-labelledby="dropdownMenuButton">
          <option
            v-for="widget in widgets"
            :key="widget.name"
            class="dropdown-item"
            @click="onChange($event)"
            :value="widget.name"
          >
            {{ widget.name }}
          </option>

          <!-- <a class="dropdown-item" href="#">Chuck Norris</a>
        <a class="dropdown-item" href="#">Cat</a>
        <a class="dropdown-item" href="#">Excuse</a>
        <a class="dropdown-item" href="#">Widget 4</a>
        <a class="dropdown-item" href="#">Widget 5</a>
        <a class="dropdown-item" href="#">Widget 6</a>
        <a class="dropdown-item" href="#">Widget 7</a> -->
        </div>
      </div>
    </nav>

    <div class="home">
      <div v-for="(widgetname, index) in widgetNames" :key="index">
        <div>
          <button class="delete" @click="deleteWidget(index)">X</button>
        </div>
        <WidgetOne v-if="widgetname === 'Chuck'" />
        <WidgetTwo v-if="widgetname === 'Cat'" />
        <WidgetThree v-if="widgetname === 'Excuse'" />
        <WidgetFour v-if="widgetname === 'Country flag'" />
        <WidgetFive v-if="widgetname === 'Logo maker'" />
        <WidgetSix v-if="widgetname === 'Cat type'" />
        <WidgetSeven v-if="widgetname === 'Currency rates'" />
      </div>
    </div>
  </body>
</template>

<script >
import WidgetOne from "@/components/widgetOne.vue";
import WidgetTwo from "@/components/widgetTwo.vue";
import WidgetThree from "@/components/widgetThree.vue";
import WidgetFour from "@/components/widgetFour.vue";
import WidgetFive from "@/components/widgetFive.vue";
import WidgetSix from "@/components/widgetSix.vue";
import WidgetSeven from "@/components/widgetSeven.vue";
// @ is an alias to /src

const widgetNames = [];

export default {
  name: "HomeView",
  components: {
    WidgetOne,
    WidgetTwo,
    WidgetThree,
    WidgetFour,
    WidgetFive,
    WidgetSix,
    WidgetSeven,
  },
  data() {
    return {
      widgetNames,
      myChoice: "",
      widgets: [
        {
          name: "Chuck",
        },
        {
          name: "Cat",
        },
        {
          name: "Excuse",
        },
        {
          name: "Country flag",
        },
        {
          name: "Logo maker",
        },
        {
          name: "Cat type",
        },
        {
          name: "Currency rates",
        },
      ],
    };
  },

  methods: {
    onChange(event) {
      this.widgetNames.push(event.target.value);
      console.log(this.widgetNames);
      // this.myChoice=event.target.value
      // console.log(this.myChoice)
    },
    deleteWidget(index) {
      // this.index = this.key;
      // console.log(parseFloat(this.index))
      // console.log()
      console.log(index);
      console.log(this.widgetNames);
      this.widgetNames.splice(index, 1);
    },
  },
};
</script>
<style lang="css">
.delete {
  position: relative;
  top: 115px;
  right: -35%;
  cursor: pointer;
  border: none;
  background: none;
}

.home {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  flex-wrap: wrap;
}
</style>
<!-- <style scoped> 
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@4.0.0/dist/css/bootstrap.min.css" integrity="sha384-Gn5384xqQ1aoWXA+058RXPxPg6fy4IWvTNh0E263XmFcJlSAwiGgFAW/dAiS6JXm" crossorigin="anonymous">

.header {
  background-color: #bfced8;
  padding: 40px;
  margin-top: 0%;
  font-family: "Playfair Display", serif;
  text-align: left;
  color: white;
}

#add2 {
  color: white;
  display: flex;
  justify-content: space-between;
  margin-top: -6%;
  margin-left: 85%;
  font-weight: 900;
}
#add {
  display: flex;
  text-decoration: none;
  color: black;
  justify-content: space-between;
  margin-left: 93%;
  margin-top: -3.1%;
  font-size: 30px;
}
</style>-->