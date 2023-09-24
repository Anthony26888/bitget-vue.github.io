<template lang="">
    <div class="container mt-5">
        <div class="d-flex justify-content-between">
            <h3 class="mt-3">Martket</h3>
            <div class="input-group">
                <span class="input-group-text" id="basic-addon1"><i class="bi bi-search"></i></span>
                <input type="text" class="form-control" placeholder="Search coin" aria-label="Search coin" aria-describedby="basic-addon1">
            </div>
        </div>
        <div class="table-responsive mt-5">
            <table class="table table-dark table-hover table-xl" >
                <thead slot="head">
                    <tr>                 
                        <th class="text-start col-xl-2">{{column1}}</th>
                        <th class="text-end col-xl-2" >{{column2}}</th>
                        <th class="text-end col-xl-2" >{{column3}}</th>
                        <th class="text-end col-xl-2" >{{column4}}</th>
                        <th class="text-end col-xl-2" >{{column5}}</th>
                        <th class="text-end col-xl-2" >{{column6}}</th>
                    </tr>  
                </thead>
                <tbody>
                    <tr v-for="(value, index) in Market">
                        <template v-if="index <20">
                            <td class="d-flex align-item-center">
                                <i class="bi bi-star"></i>
                                <img class="ms-3" :src="value.image" :alt="value.symbol">                    
                                <p class="symbol-coin ms-3">{{value.symbol}}/USDT</p>
                            </td>
                           <td class="text-end">{{value.current_price.toLocaleString()}}</td>
                           <td v-if="value.price_change_percentage_24h>0" class="text-end text-green">{{value.price_change_percentage_24h.toFixed(2)}}%</td>
                           <td v-else class="text-end text-red">{{value.price_change_percentage_24h.toFixed(2)}}%</td>
                           <td class="text-end">{{value.total_volume.toLocaleString()}}</td>
                           <td class="text-end">
                                <img class="container sparkline" v-if="value.price_change_percentage_24h > 0" :src="`https://quickchart.io/chart?c={type:'sparkline',data:{datasets:[{fill:false,borderWidth:15,borderColor:'rgb(1 188 141)', lineTension: 0.4,data:[` +value.sparkline_in_7d.price.slice(150,200) +']}]}}'" />
                                <img class="container sparkline" v-else :src="`https://quickchart.io/chart?c={type:'sparkline',data:{datasets:[{fill:false,borderWidth:15,borderColor:'rgb(241 73 63)', lineTension: 0.4,data:[` +value.sparkline_in_7d.price.slice(150,200) +']}]}}'" />
                           </td>
                           <td class="text-end text-trade">Trade</td>
                        </template>
                    </tr>                    
                </tbody>
            </table>
        </div>
        
    </div>
</template>
<script>
import axios from 'axios';

export default {
    data() {
        return {            
            column1:'Trading pair',
            column2:'Last price',
            column3:'24h change',
            column4:'Vol',
            column5:'24h chart',
            column6:'Action',
            
            Market: {},
        }
    },
    mounted() {
        this.fetchData();
    },
    methods: {
        fetchData(){
            const url= 'https://api.coingecko.com/api/v3/coins/markets?vs_currency=usd&order=market_cap_desc&per_page=250&page=1&sparkline=true&locale=en';

            axios
                .get(url)
                .then((response) =>{
                    this.Market = response.data
                })
                .catch((error) =>{
                    console.log('Error fetching and parsing data', error);
                })
        }
    },
}
</script>
<style scoped>
    h3{
        color: var(--white);
    }
    .input-group{
        width: 240px;
        height: 42px;
        
    }
    input{
        background-color: transparent;
        border-radius: 48px;
        border-color: var(--border);
    }

    input:focus{
        background-color: transparent;
        border-radius: 48px;
        border-color: var(--border);
        color: var(--white);
    }

    input::placeholder{
        color:var(--white)
    }
    .input-group-text{
        background-color: transparent;
        color: var(--white);
        border-radius: 48px;
        border-color: var(--border);
    }

    .table th{
        background-color: transparent;
        font-size: 14px;
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

    .sparkline{
        width: 124px;
        height: 40px;
    }

    .bi-star *{
        fill: yellow;
    }

    .text-trade{
        color: var(--blue);
    }
</style>