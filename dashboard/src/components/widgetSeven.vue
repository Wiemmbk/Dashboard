<template>
    <div class="currency">
<div class="title7">
        <h1>Exchange rate</h1></div>
        <div>

            <div class="selectOne">
            <select v-model="from">
                <option selected>currency</option>
                <option value="USD">Dollar</option>
                <option value="EUR">Euro</option>
                <option value="JPY">Yen </option>
                <option value="GBP">Livre Sterling</option>
                <option value="CHF">Franc suisse</option>
            </select></div>
            <div class="to"><p>to</p></div>
            <div class="selectTwo"><select v-model="to">
                <option selected>currency</option>
                <option value="USD">Dollar</option>
                <option value="EUR">Euro</option>
                <option value="JPY">Yen </option>
                <option value="GBP">Livre Sterling</option>
                <option value="CHF">Franc suisse</option>
            </select></div>
            <div class="convert"><button v-on:click="convert">Show exchange rate</button><br></div>
          <div class="resultRate"> <p>{{ currencyRate}}</p></div> 
          <div class="refreshRate">
      <button @click="reload()"><img src="../assets/refresh.png" /></button
      ><br />
    </div>
        </div>


    </div>
</template>

<script>
import axios from 'axios'
export default {
    name: "widgetSeven",

    data() {

        return {
            from: [
                'USD',
                'EUR',
                'JPY',
                'GBP',
                'CHF'
            ],
            to: [
                'USD',
                'EUR',
                'JPY',
                'GBP',
                'CHF'
            ],
            currencyRate: null,
        }
    },
    methods: {
    convert() {
            axios.get('https://api.exchangerate.host/convert?from='+ this.from+'&to='+ this.to)
        .then((response) => {
            this.currencyRate = response.data.result;
            console.log(this.currencyRate)
        })
        },
        reload() {
      this.to = "";
      this.from = "";
      this. currencyRate="";
    },
    }
}
</script>

<style lang="css">
.currency {
    display: flex;
  align-items: flex-end;
  flex-direction: column;
  background-color: #c2bda07b;
  min-height: 16em;
  width: 350px;
  height: 200px;
  margin: 30px;
  margin-top: 80px;
  border-radius: 10%;
}
.title7 h1 {
  position: relative;
  right: 103%;
  top: 50%;
  font-size:large;
  font-weight: bolder;
}

.selectOne select{
    position: relative;
  top: 35px;
  right: 115%;
  border: SOLID #c2bda0;
  border-radius: 3%;
  background: #c2bda07b;
  cursor: pointer;
}

.to{
    position: relative;
    top: 10px;
  right: 59%;

}
.selectTwo select{
position: relative;
  top: -31px;
  right: 6%;
  border: SOLID #c2bda0;
  border-radius: 3%;
  background: #c2bda07b;
  cursor: pointer;

}

.convert button {
    position: relative;
    right: 55%;
    border: SOLID #c2bda0;
  border-radius: 3%;
  background: #c2bda07b;
}
.resultRate{
    position: relative;

    right: 87px;
}
.refreshRate button {
  position: relative;
  right: 15%;
  top: 8%;
  cursor: pointer;
  border: none;
  background: none;
}
.refreshRate img {
  position: relative;
  height: 20px;
  width: 20px;
  right: 160px;
  bottom: 45px;
}
</style>
