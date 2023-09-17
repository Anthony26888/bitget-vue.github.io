<template lang="">
  <ul class="dropdown-menu dropdown-menu-dark columns-1">
    <li class="d-flex">
      <div class="dropdown-item d-flex">
        <img class="icon-nav" src="./icon/credit-icon.png" alt="" />
        <div class="p-2">
          <a href="" class="content-nav">{{ Link1 }}</a
          ><br />
          <small>{{ LinkSmall1 }}</small>
        </div>
      </div>
    </li>
    <li class="d-flex">
      <div class="dropdown-item d-flex">
        <img class="icon-nav" src="./icon/p2p-icon.png" alt="" />
        <div class="p-2">
          <a href="" class="content-nav">{{ Link2 }}</a
          ><br />
          <small>{{ LinkSmall2 }}</small>
        </div>
      </div>
    </li>
    <li class="d-flex">
      <div class="dropdown-item d-flex">
        <img class="icon-nav" src="./icon/thirty-party-icon.png" alt="" />
        <div class="p-2">
          <a href="" class="content-nav">{{ Link3 }}</a
          ><br />
          <small>{{ LinkSmall3 }}</small>
        </div>
      </div>
    </li>
  </ul>
</template>
<script>
export default {
  data() {
    return {
      Link1: "Credit / Debit Card",
      LinkSmall1: "Buy crypto via VISA or Mastercard",

      Link2: "P2P trading",
      LinkSmall2: "Buy crypto from verified merchants",

      Link3: "Thirty-party",
      LinkSmall3: "Buy crypto through Simplex, Banxa, or Mercuryo",
    };
  },
};
</script>
<style scoped>
.columns-1 {
  width: 350px;
}




</style>
