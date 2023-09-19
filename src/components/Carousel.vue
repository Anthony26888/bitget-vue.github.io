

<style lang="">
  
</style>
<template> 
  <div class="container mt-5 justify-content-center align-items-center">
    <small class="text-light small-nav">Bitget / Markets / Overview</small>
    <div class="d-flex justify-content-between">
      <h1 class="flex-row text-light">Markets</h1>
      <div class="d-flex ">
        <img src="img/icon/ranking-white.a4ddce4.png.png" alt="" style="width: 28px; height: 28px;">
        <h5 class="text-light flex-row-reverse">Rankings</h5>
      </div>
    </div>
    <div id="carouselId" class="carousel slide m-5 " data-bs-ride="carousel">
      <ol class="carousel-indicators">
        <li data-bs-target="#carouselId" data-bs-slide-to="0" class="active" aria-current="true" aria-label="First slide"></li>
        <li data-bs-target="#carouselId" data-bs-slide-to="1" aria-label="Second slide"></li>
        <li data-bs-target="#carouselId" data-bs-slide-to="2" aria-label="Third slide"></li>
      </ol>
      <div class="carousel-inner " role="listbox">
        <div class="carousel-item active">
          <div class="row justify-content-center">
            <div class="col" v-for="value in carousel1">
              <div class="card text-start">                
                <div class="card-body ">
                  <div class="d-flex justify-content-between">
                    <strong class="card-title">{{ value.symbol.toUpperCase() }}/USDT</strong>
                    <small class="card-text">{{ value.price_change_percentage_24h.toFixed(2) }} %</small>
                  </div>
                  <img class="container sparkline" src="https://quickchart.io/chart?c={type:'sparkline',data:{datasets:[{fill:false,borderWidth:5,borderColor:'red',data:[140,60,274,370,199]}]}}" />
                  <div class="d-flex justify-content-between">
                    <img class="icon-coin" :src="value.image" alt="">
                    <strong class="card-text">$ {{ value.current_price.toLocaleString() }}</strong>
                  </div>
                </div>
              </div>
            </div>            
          </div>
        </div>
        <div class="carousel-item">
          <div class="row justify-content-center">
            <div class="col" v-for="value in carousel2">
              <div class="card text-start">                
                <div class="card-body ">
                  <div class="d-flex justify-content-between">
                    <strong class="card-title">{{ value.symbol.toUpperCase() }}/USDT</strong>
                    <small class="card-text">{{ value.price_change_percentage_24h.toFixed(2) }} %</small>
                  </div>
                  <img class="container sparkline" src="https://quickchart.io/chart?c={type:'sparkline',data:{datasets:[{fill:false,borderWidth:5,borderColor:'red',data:[140,60,274,370,199]}]}}" />
                  <div class="d-flex justify-content-between">
                    <img class="icon-coin" :src="value.image" alt="">
                    <strong class="card-text">$ {{ value.current_price.toLocaleString() }}</strong>
                  </div>
                </div>
              </div>
            </div>    
          </div>          
        </div>
        <div class="carousel-item">
          <div class="row justify-content-center">
            <div class="col" v-for="value in carousel3">
              <div class="card text-start">                
                <div class="card-body ">
                  <div class="d-flex justify-content-between">
                    <strong class="card-title">{{ value.symbol.toUpperCase() }}/USDT</strong>
                    <small class="card-text">{{ value.price_change_percentage_24h.toFixed(2) }} %</small>
                  </div>
                  <img class="container sparkline" src="https://quickchart.io/chart?c={type:'sparkline',data:{datasets:[{fill:false,borderWidth:5,borderColor:'red',data:[140,60,274,370,199]}]}}" />
                  <div class="d-flex justify-content-between">
                    <img class="icon-coin" :src="value.image" alt="">
                    <strong class="card-text">$ {{ value.current_price.toLocaleString() }}</strong>
                  </div>
                </div>
              </div>
            </div>    
          </div>      
        </div>
      </div>
      <button class="carousel-control-prev justify-content-start" type="button" data-bs-target="#carouselId" data-bs-slide="prev">
        <span class="carousel-control-prev-icon" aria-hidden="true"></span>
        <span class="visually-hidden">Previous</span>
      </button>
      <button class="carousel-control-next justify-content-end" type="button" data-bs-target="#carouselId" data-bs-slide="next">
        <span class="carousel-control-next-icon" aria-hidden="true"></span>
        <span class="visually-hidden">Next</span>
      </button>
    </div>
  </div>
  
  
</template>
<script>    
  import axios from 'axios';

  export default {
    data() {
      return {
        carousel1: {},
        carousel2: {},
        carousel3: {},
      };
    },
    mounted() {
      this.fetchCoinData();    
    },
    methods: {

      
      fetchCoinData() {
        const coin1 = 'bitcoin';
        const coin2 = 'ethereum';
        const coin3 = 'binancecoin';
        const coin4 = "litecoin";
        const coin5 = "ripple";
        const coin6 = "dogecoin";
        const coin7 = "cardano";
        const coin8 = "arpa";
        const coin9 = "kaspa"
        const apiUrl1 = `https://api.coingecko.com/api/v3/coins/markets?vs_currency=usd&ids=${coin1}%2C${coin2}%2C${coin3}&page=1&sparkline=true&price_change_percentage=24h&locale=en&precision=3`;
        const apiUrl2 = `https://api.coingecko.com/api/v3/coins/markets?vs_currency=usd&ids=${coin4}%2C${coin5}%2C${coin6}&page=1&sparkline=true&price_change_percentage=24h&locale=en&precision=3`;
        const apiUrl3 = `https://api.coingecko.com/api/v3/coins/markets?vs_currency=usd&ids=${coin7}%2C${coin8}%2C${coin9}&page=1&sparkline=true&price_change_percentage=24h&locale=en&precision=3`;
        axios
          .get(apiUrl1)
          .then((response) => {
            this.carousel1 = response.data;
          })
          .catch((error) => {
            console.error('Error fetching data:', error);
          });

        axios
          .get(apiUrl2)
          .then ((response) => {
            this.carousel2 = response.data;
          })
          .catch((error) => {
            console.error('Error fetching data:', error);
          });

        axios
          .get(apiUrl3)
          .then ((response) => {
            this.carousel3 = response.data;
          })
          .catch((error) => {
            console.error('Error fetching data:', error);
          })
      },

      
      
    },
  };

</script>
<style scoped>
  .card{
    width: 384px;
    height: 216px;
    border:1px solid rgb(66 66 66);
    border-radius: 16px;
    box-shadow: rgb(157 193 203 / 0.1) 0px 10px 32px 0px;
    background-color: rgb(25 26 26 / 0.4);
    color: var(--white);
    font-size: 14px;
    line-height:20px;
    padding: 16px 0;
  }

  .carousel{
    
    max-width: fit-content;
  }

  .sparkline{    
    width: 350px;
    height: 95px;
    border-width: 5px;
  }

  .icon-coin{
    width: 32px;
    height: 32px;
  }
</style>