<script setup>
</script>
<template lang="">
    <div>
        <nav class="navbar navbar-expand-sm navbar-dark" style="background-color: var(--bg)">
            <a class="navbar-brand ms-2" href="#">
                <img :src="'/src/assets/img/Logo-Bitget/' + logo" alt="">
            </a>
            <button class="navbar-toggler d-lg-none" type="button" data-bs-toggle="collapse" data-bs-target="#collapsibleNavId" aria-controls="collapsibleNavId"
                aria-expanded="false" aria-label="Toggle navigation"></button>
            <div class="collapse navbar-collapse" id="collapsibleNavId">
                <ul class="navbar-nav me-auto mt-2 mt-lg-0">
                    <li class="nav-item dropdown">
                        <a class="nav-link dropdown-toggle" href="#" id="dropdownId" data-bs-toggle="dropdown" aria-haspopup="true" aria-expanded="false">{{nav1}}</a>
                        <ul class="dropdown-menu dropdown-menu-dark columns-1 mt-2" >
                            <li class="d-flex" v-for="value in LinkBuyCrypto">
                                <div class="dropdown-item d-flex">
                                    <img :src="'/src/assets/img/icon/' + value.url" class="icon-nav" alt="" />        
                                    <div class="p-2">
                                        <a href="" class="content-nav">{{ value.content }}</a><br />
                                        <span class="small-nav">{{ value.sub }}</span>
                                    </div>
                                </div>
                            </li>    
                        </ul>
                    </li>
                    <li class="nav-item dropdown">
                        <a class="nav-link dropdown-toggle" href="#" id="dropdownId" data-bs-toggle="dropdown" aria-haspopup="true" aria-expanded="false">{{nav2}}</a>
                        <ul class="dropdown-menu dropdown-menu-dark columns-2 mt-2" >
                            <li class="d-flex" v-for="value in LinkMarket">
                                <div class="dropdown-item d-flex">
                                    <img :src="'/src/assets/img/icon/' + value.url" class="icon-nav" alt="" />        
                                    <div class="p-2">
                                        <a href="" class="content-nav">{{ value.content }}</a><br />
                                        <span class="small-nav">{{ value.sub }}</span>
                                    </div>   
                                </div>
                            </li>    
                        </ul>
                    </li>
                    <li class="nav-item dropdown">
                        <a class="nav-link dropdown-toggle" href="#" id="dropdownId" data-bs-toggle="dropdown" aria-haspopup="true" aria-expanded="false">{{nav3}}</a>
                        <ul class="dropdown-menu dropdown-menu-dark columns-3 mt-2" >
                            <li class="d-flex" v-for="value in LinkTrade">
                                <div class="dropdown-item d-flex">
                                    <img :src="'/src/assets/img/icon/' + value.url" class="icon-nav" alt="" />        
                                    <div class="p-2">
                                        <a href="" class="content-nav">{{ value.content }}</a><br />
                                        <span class="small-nav">{{ value.sub }}</span>
                                    </div>
                                </div>
                            </li>    
                        </ul>
                    </li>
                    <li class="nav-item dropdown">
                        <a class="nav-link dropdown-toggle" href="#" id="dropdownId" data-bs-toggle="dropdown" aria-haspopup="true" aria-expanded="false">{{nav4}}</a>
                        <ul class="dropdown-menu dropdown-menu-dark columns-4 mt-2" >
                            <li class="d-flex" v-for="value in LinkCopy">
                                <div class="dropdown-item d-flex">
                                    <img :src="'/src/assets/img/icon/' + value.url" class="icon-nav" alt="" />        
                                    <div class="p-2">
                                        <a href="" class="content-nav">{{ value.content }}</a><br />
                                        <span class="small-nav">{{ value.sub }}</span>
                                    </div>
                                </div>
                            </li>    
                        </ul>
                    </li>
                    <li class="nav-item dropdown">
                        <a class="nav-link dropdown-toggle" href="#" id="dropdownId" data-bs-toggle="dropdown" aria-haspopup="true" aria-expanded="false">{{nav5}}</a>
                        <ul class="dropdown-menu dropdown-menu-dark columns-5 mt-2" >
                            <div class="row justify-content-center g-2">
                                <div class="col">
                                    <li><span class="dropdown-header small-nav">Basic bots</span></li>
                                    <li class="d-flex" v-for="value in LinkBot1">
                                        <div class="dropdown-item d-flex">
                                            <img :src="'/src/assets/img/icon/' + value.url" class="icon-nav" alt="" />        
                                            <div class="p-2">
                                                <a href="" class="content-nav">{{ value.content }}</a><br />
                                                <span class="small-nav">{{ value.sub }}</span>
                                            </div>
                                        </div>
                                    </li>    
                                </div>
                                <div class="col">
                                    <li><span class="dropdown-header small-nav">Advanced bots</span></li>
                                    <li class="d-flex" v-for="value in LinkBot2">
                                        <div class="dropdown-item d-flex">
                                            <img :src="'/src/assets/img/icon/' + value.url" class="icon-nav" alt="" />        
                                            <div class="p-2">
                                                <a href="" class="content-nav">{{ value.content }}</a><br />
                                                <span class="small-nav">{{ value.sub }}</span>
                                            </div>
                                        </div>
                                    </li>  
                                </div>
                                <div class="col link-bot-3">                                    
                                    <img class="banner-bot-3 " :src="'src/assets/img/icon/' + BannerBot3" alt="">
                                  
                                </div>
                            </div>
                            
                        </ul>                        
                    </li>
                    <li class="nav-item dropdown">
                        <a class="nav-link dropdown-toggle" href="#" id="dropdownId" data-bs-toggle="dropdown" aria-haspopup="true" aria-expanded="false">{{nav6}}</a>
                        <div class="dropdown-menu" aria-labelledby="dropdownId">
                            <a class="dropdown-item" href="#">Action 1</a>
                            <a class="dropdown-item" href="#">Action 2</a>
                        </div>
                    </li>
                    <li class="nav-item dropdown">
                        <a class="nav-link dropdown-toggle" href="#" id="dropdownId" data-bs-toggle="dropdown" aria-haspopup="true" aria-expanded="false">{{nav7}}</a>
                        <div class="dropdown-menu" aria-labelledby="dropdownId">
                            <a class="dropdown-item" href="#">Action 1</a>
                            <a class="dropdown-item" href="#">Action 2</a>
                        </div>
                    </li>
                    <li class="nav-item dropdown">
                        <a class="nav-link dropdown-toggle" href="#" id="dropdownId" data-bs-toggle="dropdown" aria-haspopup="true" aria-expanded="false">{{nav8}}</a>
                        <div class="dropdown-menu" aria-labelledby="dropdownId">
                            <a class="dropdown-item" href="#">Action 1</a>
                            <a class="dropdown-item" href="#">Action 2</a>
                        </div>
                    </li>
                </ul>
                <form class="d-flex my-2 my-lg-0">
                    <input class="form-control me-sm-2" type="text" placeholder="Search">
                    <button class="btn btn-outline-success my-2 my-sm-0" type="submit">Search</button>
                </form>
            </div>
        </nav>
    </div>
 
    
</template>
<script>
    export default {
    data() {
        return {
            nav1:'Buy Crypto',
            nav2:'Market',
            nav3:'Trade',
            nav4:'Copy',
            nav5:'Bots',
            nav6:'Earn',
            nav7:'Web3',
            nav8:'KCGI',
            logo:'logo-dark.svg.svg',
            
            LinkBuyCrypto : [
                {content:'Credit / Debit Card', sub:'Buy crypto via VISA or Mastercard', url:'overview-icon.png'},
                {content:'P2P trading', sub:'Power up trades with liquidity', url:'future-copy-trade-icon.png'},
                {content:'Buy crypto from verified merchants', sub:'Trade with leverage', url:'spot-copy-trade-icon.png'},
                {content:'Bot Copy TradingThirty-party', sub:'Buy crypto through Simplex, Banxa, or Mercuryo', url:'bot-copy-trade-icon.png'},
            ],

            LinkMarket : [
                {content:'Markets', sub:'Crypto market intelligence', url:'market-icon.png'},
                {content:'Top Movers', sub:'Popular crypto rankings', url:'top-mover-icon.png'},
                {content:'Market data', sub:'Latest market data', url:'market-data-icon.png'},
                {content:'Insights', sub:'Insights from experts', url:'insight-icon.png'},
                {content:'News', sub:'Latest media articles', url:'news-icon.png'},
            ],
            
            LinkTrade : [
                {content:'Spot', sub:'Buy and sell crypto with ease', url:'spot-icon.png'},
                {content:'Futures', sub:'Power up trades with liquidity', url:'future-icon.png'},
                {content:'Margin', sub:'Trade with leverage', url:'margin-ico.png'},
                {content:'Convert', sub:'Zero fees, no slippage', url:'convert-icon.png'},
                {content:'Bitget Swap', sub:'', url:'bitget-swap-icon.png'}
            ],

            LinkCopy : [
                {content:'Overview', sub:'Introduction to Bitget copy trading and its advantages', url:'overview-icon.png'},
                {content:'Futures Copy Trading', sub:'Bring together the worlds top futures trading experts', url:'future-copy-trade-icon.png'},
                {content:'Spot Copy Trading', sub:'Follow the worlds top spot trading experts', url:'spot-copy-trade-icon.png'},
                {content:'Bot Copy Trading', sub:'Copy top bots to trade smarter', url:'bot-copy-trade-icon.png'},
                {content:'Create a trading bot', sub:'Create your own trading bot', url:'create-trade-bot-icon.png'},
                {content:'Leaderboard', sub:'Elite traders leaderboard', url:'leaderboard-icon.png'}
            ],

            LinkBot1 : [
                {content:'Spot auto-invest', sub:'Regularly invest without timing the market', url:'spot-invest-icon.png'},
                {content:'Spot grid', sub:'Automate trades with grid bots', url:'spot-grid-icon.png'},
                {content:'Futures grid', sub:'Amplify bot trades with leverage.', url:'future-grid-icon.png'},                
            ],

            LinkBot2 : [
                {content:'Spot Martingale', sub:'Automate futures investments to minimize volatility', url:'spot-martingale-icon.png'},
                {content:'Futures Martingale', sub:'Automate futures investments to minimize volatility', url:'future-martingale-icon.png'},
                {content:'Spot CTA', sub:'Intelligent short-term spot trades in diverse markets', url:'spot-cta-icon.png'}, 
                {content:'Futures CTA', sub:'Intelligent short-term futures trades in diverse markets', url:'future-cta-icon.png'},               
            ],

            BannerBot3:'banner-bot-3.png'

            
        }
    },
}
</script>

<style scoped>
    .navbar{
        height: 55px;
    }

    .columns-1{
        width: 300px;
    }

    .columns-2{
        width: 200px;
    }

    .columns-3{
        width: 220px;
    }

    .columns-4{
        width: 250px;       
    }
    .columns-5{
        width: 700px;
    }
    .banner-bot-3{
        width: 180px;
        height: 126px;        
    }
   
</style>
