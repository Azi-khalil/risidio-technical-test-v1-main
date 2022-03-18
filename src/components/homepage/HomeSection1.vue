<template>
  <div class="title">
    <h1>Collection Name</h1>
  </div>
  <div class="banner">
    <img src="../../assets/face.png" />
      <h3>Artist Name</h3>
    <div class="description">
      <p>Description of the NFT / collectable - Examples such the content of NFTs, specific themes of the collection, quotations by the creator, the meaning behind the creation of this piece…</p>
      <p :class="isActive ? 'shown' : 'hidden'">Description of this collection - - Examples such the content of NFTs, specific themes of the collection, quotations by the creator, the meaning behind the creation of this collection etc Description of this collection - - Examples such the content of NFTs, specific themes of the collection, quotations by the creator, the meaning behind the creation of this collection etcDescription of this collection - - Examples such the content of NFTs, specific themes of the collection, quotations by the creator, the meaning behind the creation of this collection etc</p>
      <button @click="showP">{{isActive ? 'Hide' : 'Read More'}}</button>
    </div>
    <div class="detail-list">
      <div>
        <li>Floor Price</li>
        <span>2,835 STX</span>
      </div>
      <div class="borders">
        <li>Owners</li>
        <span>1,236</span>
      </div>
      <div>
        <li>Items</li>
        <span>2,500</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HomeSection1',
  data () {
    return{
      isActive: false,
    }
  },
  methods: {
    showP(){
      return this.isActive = !this.isActive
    }
  } 
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.title{
  background-image:
    linear-gradient(to bottom, #000000, #0000003C),
    url("../../assets/sec-banner.png");
  background-repeat: no-repeat;
  background-size: cover;
  width: 100%;
  height: 132px;
  background-repeat: no-repeat;
  position: absolute;
  display: flex;
  justify-content: center;
  align-items: center;
}
.title h1 {
  font: normal normal 300 40px/55px Montserrat;
  letter-spacing: 0px;
  color: #FFFFFF;
  text-transform: capitalize;
}

.banner{
  display: flex;
  justify-content: center;
  flex-direction: column;
  align-items: center;
  text-align: center;
}

.banner img {
  margin-top: 100px;
  z-index: 10;
  width: 94px;
  height: 94px;
  background: 0% 0% no-repeat padding-box;
  opacity: 1;
}
.banner h3{
  font: normal normal medium 18px/22px Montserrat;
}
.description{
  width: 576px;
}

.description button{
  background: none;
  border: none;
  font: normal normal 600 14px/20px Montserrat;
  letter-spacing: 0px;
  color: #50B1B5;
  opacity: 1;
}
.description p{
  font: normal normal normal 14px/20px Montserrat;
}
.shown{
  display: block;
}
.hidden{
  display: none;
}
.detail-list{
  display: flex;
  justify-content: space-around;
  flex-direction: row;
  align-items: center;
  width: 611px;
  height: 93px;
  background: #F9F9F9 0% 0% no-repeat padding-box;
  border-radius: 25px;
  margin-top: 30px;
}
.detail-list li{
  margin-bottom: 10px;
  list-style-type: none;
}
.detail-list span{
  font-weight: 700;
}
.borders{
  border-right: 1px solid lightgray;
  border-left: 1px solid lightgray;
  padding: 0px 60px;
}
@media (max-width: 428px) {
  .title{
    height: 207px;
  }
  .banner img{
    margin-top: 137px;
    width: 149px;
    height: 149px;
  }
  .description{
    width: 360px;
  }
  .detail-list{
    flex-direction: column;
    width: 202px;
    height: 450px;
  }
  .borders{
    border-right: none;
    border-left: none;
    border-top: 1px solid lightgray;
    border-bottom: 1px solid lightgray;
    padding: 60px 0px;
  }
}

</style>
