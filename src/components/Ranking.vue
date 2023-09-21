<template lang="">
  <div class="container">
    <div class="d-flex">
      <h3 class="title">Rankings</h3>
      <h4 class="sub-title ms-5">Today's crypto heatmap</h4>
      <span class="badge text-bg-warning ms-2">New</span>
    </div>
    <div class="row mt-5 container">
      <div class="col">
        <div class="card text-start">
          <div class="card-body">
            <h4 class="card-title">Gainers</h4>
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
                  <td>{{ index +1 }}</td>
                  <td class="d-flex align-item-center">
                    <img :src="value.image" alt="">                    
                    <p >{{value.symbol}}</p>
                  </td>
                  <td>{{value.current_price}}</td>
                  <td>{{value.price_change_percentage_24h}}</td>
                </tr>
              </tbody>
            </table>
          </div>
        </div>
      </div>
      <div class="col">
        <div class="card text-start">
          <div class="card-body">
            <h4 class="card-title">Trending</h4>
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
                <tr v-for="(value, index) in Trending">
                  <td>{{ index +1 }}</td>
                  <td class="d-flex align-item-center">
                    <img :src="value.item.small" alt="">                    
                    <p >{{value.item.symbol}}</p>
                  </td>
                  <td>{{value.item.price_btc}}</td>
                  <td>{{value.item.market_cap_rank}}</td>
                </tr>
              </tbody>
            </table>
          </div>
        </div>
      </div>
      <div class="col">
        <div class="card text-start">
          <div class="card-body">
            <h4 class="card-title">Gainers</h4>
            <p class="card-text">Body</p>
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
      Gainer: {},
      Trending: {},
      New: {},
    };
    

  },
  mounted() {
      this.fetchData();
  },
  methods: {
    fetchData(){
      const urlGainer= 'https://api.coingecko.com/api/v3/coins/markets?vs_currency=usd&per_page=5&page=1&sparkline=false&price_change_percentage=24h&locale=en';
      const urlTrending= 'https://api.coingecko.com/api/v3/search/trending';
      axios
        .get(urlGainer)
        .then((response) =>{
          this.Gainer = response.data;
        })
        .catch((error) =>{
          console.log('error: ', error)
        })

      axios
        .get(urlTrending)
        .then((response) =>{
          this.Trending = response.data;
        })
        .catch((error) =>{
          console.log('error: ', error)
        })
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

}
</style>
