<template>
  <ul class="dropdown-menu dropdown-menu-dark columns-1">
    <li class="d-flex">
      <div class="dropdown-item d-flex">
        <img
          class="icon-nav"
          src="./icon/market-icon.png"
          alt=""
        />
        <div class="p-2">
          <a href="" class="content-nav">{{Link1}}</a><br />
          <small>{{LinkSmall1}}</small>
        </div>
      </div>
    </li>
    <li class="d-flex">
      <div class="dropdown-item d-flex">
        <img
          class="icon-nav"
          src="./icon/top-mover-icon.png"
          alt=""          
        />
        <div class="p-2">
          <a href="" class="content-nav">{{Link2}}</a><br />
          <small>{{LinkSmall2}}</small>
        </div>
      </div>
    </li>
    <li class="d-flex">
      <div class="dropdown-item d-flex">
        <img
          class="icon-nav"
          src="./icon/market-data-icon.png"
          alt=""
        />
        <div class="p-2">
          <a href="" class="content-nav">{{Link3}}</a><br />
          <small>{{LinkSmall3}}</small>
        </div>
      </div>
    </li>
    <li class="d-flex">
      <div class="dropdown-item d-flex">
        <img
          class="icon-nav"
          src="./icon/insight-icon.png"
          alt=""
        />
        <div class="p-2">
          <a href="" class="content-nav">{{Link4}}</a><br />
          <small>{{LinkSmall4}}</small>
        </div>
      </div>
    </li>
    <li class="d-flex">
      <div class="dropdown-item d-flex">
        <img
          class="icon-nav"
          src="./icon/news-icon.png"
          alt=""
        />
        <div class="p-2">
          <a href="" class="content-nav">{{Link5}}</a><br />
          <small>{{LinkSmall5}}</small>
        </div>
      </div>
    </li>
  </ul>
</template>
<script>
export default {
    data() {
        return {
            Link1:'Markets',
            LinkSmall1:'Crypto market intelligence',

            Link2:'Top Movers',
            LinkSmall2:'Popular crypto rankings',

            Link3:'Market data',
            LinkSmall3:'Latest market data',

            Link4:'Insights',
            LinkSmall4:'Insights from experts',

            Link5:'News',
            LinkSmall5:'Latest media articles',
        }
    },
};
</script>
<style scoped>
.columns-1 {
  width: 250px;
}    
</style>
