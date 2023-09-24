<template lang="">
  <div class="container">
    <div class="d-flex">
      <h3 class="title">Rankings</h3>
      <h4 class="sub-title ms-5">Today's crypto heatmap</h4>
      <span class="badge text-bg-warning ms-2">New</span>
    </div>
    <div class="row mt-5 container">
      <div class="col-sm">
        <div class="card text-start">
          <div class="card-body">
            <h4 class="card-title">Top Trending</h4>
            <table class="table table-dark table-hover table-borderless table-sm mt-5">
              <thead>
                <tr>
                  <th scope="col">{{th1}}</th>
                  <th scope="col">{{th2}}</th>
                  <th scope="col">{{th3}}</th>
                  <th scope="col">{{th5}}</th>
                </tr>
              </thead>
              <tbody>                
                <tr v-for="(value, index) in Trending">
                  <template v-if="index <5">
                    <td>{{ index +1 }}</td>
                    <td class="d-flex align-item-center">
                      <img :src="value.item.small" alt="">                    
                      <p class="symbol-coin">{{value.item.symbol}}/BTC</p>
                    </td>
                    <td>{{value.item.price_btc.toFixed(6)}}</td>
                    <td class="text-center">{{value.item.market_cap_rank}}</td>        
                  </template>          
                </tr>
              </tbody>
            </table>
          </div>
        </div>
      </div>
      <div class="col-sm">
        <div class="card text-start">
          <div class="card-body">
            <h4 class="card-title">Top Gainers</h4>
            <table class="table table-dark table-hover table-borderless table-sm mt-5">
              <thead>
                <tr>
                  <th scope="col">{{th1}}</th>
                  <th scope="col">{{th2}}</th>
                  <th scope="col">{{th3}}</th>
                  <th scope="col">{{th4}}</th>
                </tr>
              </thead>
              <tbody>          
                    
                <tr v-for="(value, index) in Gainer">
                  <template v-if="index <5">
                    <td>{{ index +1 }}</td>
                    <td class="d-flex align-item-center">
                      <img :src="value.image" alt="">                    
                      <p class="symbol-coin">{{value.symbol}}/USDT</p>
                    </td>
                    <td>{{value.current_price.toLocaleString()}}</td>
                    <td v-if="value.price_change_percentage_24h>0" class="text-center text-green">{{value.price_change_percentage_24h}}%</td>
                    <td v-else class="text-center text-red">{{value.price_change_percentage_24h}}%</td>
                  </template>
                </tr>
              </tbody>
            </table>
          </div>
        </div>
      </div>
      <div class="col-sm">
        <div class="card text-start">
          <div class="card-body">
            <h4 class="card-title">Top Losser</h4>
            <table class="table table-dark table-hover table-borderless table-sm mt-5">
              <thead>
                <tr>
                  <th scope="col">{{th1}}</th>
                  <th scope="col">{{th2}}</th>
                  <th scope="col">{{th3}}</th>
                  <th scope="col">{{th4}}</th>
                </tr>
              </thead>
              <tbody>                
                <tr v-for="(value, index) in Losser">
                  <template v-if="index <5">
                    <td>{{ index +1 }}</td>
                    <td class="d-flex align-item-center">
                      <img :src="value.image" alt="">                    
                      <p class="symbol-coin">{{value.symbol}}/USDT</p>
                    </td>
                    <td>{{value.current_price.toLocaleString()}}</td>
                    <td v-if="value.price_change_percentage_24h>0" class="text-center text-green">{{value.price_change_percentage_24h}}%</td>
                    <td v-else class="text-center text-red">{{value.price_change_percentage_24h}}%</td>
                  </template>
                </tr>
              </tbody>
            </table>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import axios from 'axios';
export default {
  data() {
    return {
      th1:'#',
      th2:'Trading pair',
      th3:'Last price',
      th4:'24h change',
      th5:'Marketcap Rank',
      
      Gainer: {},
      Trending: {},
      Losser: {},
    };
    

  },
  mounted() {
      this.fetchData();
  },
  methods: {
    fetchData(){
      const urlGainer= 'https://api.coingecko.com/api/v3/coins/markets?vs_currency=usd&order=market_cap_desc&per_page=250&page=1&sparkline=false&locale=en';
      const urlTrending= 'https://api.coingecko.com/api/v3/search/trending';
      axios
        .get(urlGainer)
        .then((response) =>{
          this.Gainer = response.data;
          this.Gainer.sort(this.compareGainer);
          
        })
        .catch((error) =>{
          console.log('error: ', error)
        })

        axios
          .get(urlGainer)
          .then((response) =>{
            this.Losser = response.data;
            this.Losser.sort(this.compareLosser);
          })
          .catch((error) =>{
            console.log('error: ', error)
          })


      axios
        .get(urlTrending)
        .then((response) =>{
          this.Trending = response.data.coins;
        })
        .catch((error) =>{
          console.log('error: ', error)
        })
    },
    compareGainer(a,b){
      if (a.price_change_percentage_24h > b.price_change_percentage_24h)
        return -1;
      if (a.price_change_percentage_24h < b.price_change_percentage_24h)
        return 1;
      return 0;
    },
    compareLosser(a,b){
      if (a.price_change_percentage_24h < b.price_change_percentage_24h)
        return -1;
      if (a.price_change_percentage_24h > b.price_change_percentage_24h)
        return 1;
      return 0;
    }
  },
 
};
</script>
<style scoped>
.title {
  color: var(--white);
}

.sub-title {
  color: var(--white);
  opacity: 0.8;
}
.sub-title:hover {
  opacity: 1;
}

.badge{
  width: 40px;
  height: 20px;
}

.card {
  background-color: transparent;
  border-color: var(--border);
}

.card-title {
  color: var(--white);
}



.table th{
  background-color: transparent;
  font-size: 12px;
  line-height: 23px;
  color: var(--gray);
}

.table td {
  background-color: transparent;
}

.table tr {
  background-color: transparent;
}

img{
  width: 28px;
  height: 28px;
  margin-top: -2px;
  margin-right: 5px;
}

.text-red{
  color: var(--red);
}
.text-green{
  color: var(--green);
}

.symbol-coin{
  text-transform: uppercase;
}
</style>
