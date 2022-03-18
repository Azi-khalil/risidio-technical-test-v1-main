<!-- You may notice this navbar is not responsive-->
<!-- We would like you to style it so it is responsive-->
<!-- You do not need to make the dropdown menu on the "Featured Collections" -->
<template>
    <div class="nav-bar">
        <div class="navbar_container">
            <img class="nav_banner" src="https://res.cloudinary.com/risidio/image/upload/v1633609222/RisidioMarketplace/gradienta-m_-1_v4hs5p.svg" alt="">
        </div>
         <div class = "mainNavbar">
            <div class="logo-container">
              <img class="logo" :src="logo" alt="risidio-logo"/>
              <img 
                class="toggle"
                :src="isActive ? require('../../assets/close.png') : require('../../assets/Menu_icon.png')"
                @click="showList">
            </div>
            <div :class="isActive ? 'links active' : 'links'">
              <li class="nav-item bold" > Gallery </li>
              <li class="nav-item bold"> Featured Collections </li>
              <img class="nav-item" src="../../assets/arrow.svg" />
              <div class="grey-border"></div>
              <li class="nav-item right"> How It Works</li>
              <li class="nav-item"> about Risidio</li>
              <li class="nav-item myNft"><span > My NFTs</span></li>
              <button>Register with Hiro Wallet</button>
            </div>
            <div :class="isActive ? 'overlay' : ''"></div>
         </div>
    </div>
</template>

<script>
export default {
  data () {
    return{
      logo: 'https://res.cloudinary.com/risidio/image/upload/v1633609248/RisidioMarketplace/Group_-1_fgpanq.svg',
      isActive: false,
    }
  },
  methods: {
    showList(){
      return this.isActive = !this.isActive
    }
  }
}
</script>

<style scoped>
.toggle{
  display: none;
  width: 25px;
  height: 22px;
  cursor: pointer;
}
.mainNavbar {
  padding: 15px 50px 20px 50px;
  display: flex;
  flex-direction: row;
  align-items: center;
}
.links{
  width: 100%;
  display: flex;
  flex-direction: row;
  align-items: center;
}
.links button{
  display: none;
}
.risidio-logo{
  align-self: flex-start;
}
.nav-item{
  list-style-type: none;
  margin: 0 20px;
  color: white;
  font-size: 12px;
  line-height: 15px;
  cursor: pointer;
}
.right {
  margin-left: auto;
}

.nav_banner{
  position: absolute;
  top: 0px;
  width: 100%;
  height: 100px;
  object-fit: cover;
  z-index: -11;
}
.myNft{
  width: 133px;
  height: 43px;
  background: rgba(255, 255, 255, 0.2);
  border-radius: 22px;
  display: flex;
  justify-content: center;
  align-items: center;
}  
.myNft span{
  font: normal normal bold 12px/15px Montserrat;
  color: #5FBDC1;
}
.grey-border{
  display: none;
}



@media (max-width: 428px) {
  .mainNavbar {
    padding: 0px;
    flex-direction: column;
  }
  .logo-container{
    padding: 13px 20px;
    width: 100%;
    display: flex;
    justify-content: space-between;
    align-items: center;
    background-image: url("../../assets/backdrop.svg");
    z-index: 20;
  }
  .links{
    position: absolute;
    top: 70px;
    display: none;
    flex-direction: column;
    align-items: flex-start;
    padding: 20px 20px 20px 20px;
    gap: 20px;
    width: 100%;
    z-index: 20;
    background-image: url("../../assets/backdrop.svg");
  }
  .links.active{
    display: flex;
  }
  .bold{
    font-weight: 700;
  }
  .links img{
    display: none;
  }
  .links button{
    display: block;
  }
  .right{
    margin-left: 20px;
  }
  .grey-border{
    display: block;
    margin: 30px 20px 30px 20px;
    height: 1px;
    width: 80%;
    background-color: lightgray;
    opacity: 0.2;
  }
  .toggle{
    display: block;
  }
  .myNft{
    display: none;
  }
  .mainNavbar button{
    background:rgba(80, 177, 181, 0.2);
    border-radius: 22px;
    font: normal normal bold 11px/14px Montserrat;
    color: #5FBDC1;
    width: 90%;
    margin-top: 60px;
    height: 43px;
    border: none;
  }
  .logo{
    width: 97px;
    height: 44px;
  }
  .nav_banner{
    height: 70px;
  }
  .overlay {
    position: fixed;
    width: 100%;
    height: 100%;
    z-index: -1; 
    background: white;
    z-index: 19;
  }
}

</style>