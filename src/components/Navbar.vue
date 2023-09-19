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
                                <div class="col link-bot-3 d-flex flex-column gap-5 justify-content-center align-items-center">                                    
                                    <img class="banner-bot-3 " :src="'src/assets/img/banner/' + BannerBot3" alt="">
                                    <button class="button-detail">Detail</button>
                                </div>
                            </div>
                        </ul>                        
                    </li>
                    <li class="nav-item dropdown">
                        <a class="nav-link dropdown-toggle" href="#" id="dropdownId" data-bs-toggle="dropdown" aria-haspopup="true" aria-expanded="false">{{nav6}}</a>
                        <ul class="dropdown-menu dropdown-menu-dark columns-6 mt-2" >
                            <div class="row justify-content-center g-2">
                                <div class="col">
                                    <li><span class="dropdown-header small-nav">Basic bots</span></li>
                                    <li class="d-flex" v-for="value in LinkEarn1">
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
                                    <li><span class="dropdown-header mt-4 "></span></li>
                                    <li class="d-flex" v-for="value in LinkEarn2">
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
                                    <li><span class="dropdown-header small-nav">Promotions</span></li>
                                    <li class="d-flex" v-for="value in LinkEarn3">
                                        <div class="dropdown-item d-flex">
                                            <img :src="'/src/assets/img/icon/' + value.url" class="icon-nav" alt="" />        
                                            <div class="p-2">
                                                <a href="" class="content-nav">{{ value.content }}</a><br />
                                                <span class="small-nav">{{ value.sub }}</span>
                                            </div>
                                        </div>
                                    </li>                                  
                                </div>
                                <div class="col link-bot-3 d-flex flex-column gap-5 justify-content-center align-items-center">                                    
                                    <img class="banner-bot-3 " :src="'src/assets/img/banner/' + BannerEarn4" alt="">
                                    <button class="button-detail">Detail</button>
                                </div>
                            </div>
                        </ul>    
                    </li>
                    
                </ul>
            
                <ul class="nav navbar-dark justify-content-beween  ">
                    <li class="nav-item">
                        <a class="nav-link active" href="#" aria-current="page">Login</a>
                    </li>
                    <li class="nav-item">
                        <button class="button-signUp">Sign Up</button>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="#" aria-current="page"><i class="bi bi-search"></i></a>                        
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="#" aria-current="page"><i class="bi bi-bell"></i></a>                        
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="#" aria-current="page"><i class="bi bi-layout-text-sidebar"></i></a>                        
                    </li>
                </ul>
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

            LinkEarn1 : [
                {content:'Overview', sub:'Comprehensive investment and financial management', url:'overview-icon.png'},
                {content:'Savings', sub:'Earn daily profits with idle tokens', url:'saving-icon.png'},
                {content:'Staking', sub:'Guaranteed earnings in both bear and bull markets', url:'stacking-icon.png'},
                {content:'BGB Staking', sub:'Stake BGB for zero-fee withdrawals', url:'bgb-stacking-icon.png'},
                {content:'Crypto Loans', sub:'Borrow crypto quickly and easily', url:'crypto-loans-icon.png'},                
            ],

            LinkEarn2 : [
                {content:'Dual Investment', sub:'Buy low and sell high — profit no matter the market direction', url:'dual-invest-icon.png'},
                {content:'Shark Fin', sub:'Principal-guaranteed high yields', url:'shark-fin-icon.png'},
                {content:'Smart Trend', sub:'Time the market and enjoy incredible yields', url:'smart-trend-icon.png'}, 
                {content:'Snowball', sub:'Principal-protected explosive earning potential', url:'snow-icon.png'}, 
                {content:'Range Sniper', sub:'Profit from predicting price ranges', url:'range-sniper-icon.png'},              
            ],

            LinkEarn3 : [
                {content:'Launchpad', sub:'Get ahead with hot and new tokens', url:'lauchpad-icon.png'},
                {content:'Launchpool', sub:'Stake and mine hot and new tokens', url:'lauchpool-icon.png'},                
                {content:'BGB Zone', sub:'All BGB rewards in one place', url:'bgb-zone-icon.png'}, 
                {content:'Bitget wealth management', sub:'Grow your wealth with our top-tier asset management team.', url:'bitget-wealth-icon.png'},              
            ],

            BannerBot3:'banner-bot-3.png',
            BannerEarn4:'banner-earn-4.png'

            
        }
    },
}
</script>

<style scoped>
    .navbar{
        height: 55px;
    }
    .nav-link{
        color: var(--white);
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

    .columns-6{
        width: 900px;
    }
    .banner-bot-3{
        width: 180px;
        height: 126px;        
    }

    .dropdown-menu{
        background-color: var(--bg);
    }
   
    .button-detail{
        width: 150px;
        height: 40px;
        border-radius: 10px;
    }

    .button-signUp{
        border-radius: 20px;
        padding: 8px 15px;
    }

    i{
        font-size: 22px;
        color: white;
    }
</style>
