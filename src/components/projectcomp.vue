<template>
  <div class="project-comp box">
    <div class="img-box">
      <img :src="this.imgSrc" alt="" />
    </div>
    <div class="discrptions dis-box">
      <p class="disc-p"><fontawesome-icon :icon="['fa', 'building']"
          /> {{ discription }}</p>

      <p class="location-p"><fontawesome-icon :icon="['fa', 'map-pin']"
          /> {{ location }}</p>
    </div>
    <div class="view-btn">
      <button @click="viewProjectImg" :class="'ptnViewDetails' + pstNo">
        <a href="#" class="fa fa-eye"></a>
        <p>View</p>
      </button>
    </div>
  </div>
</template>
<script>
export default {
  name: "projectComp",
  props: ["title", "discription", "imgSrc", "location"],
    methods:{
    viewProjectImg: function(){
      document.getElementById("view-project-box").style.display = "block";
      document.getElementById("big-img").src = this.imgSrc ; 
    },
  },
};
</script>
<style lang="scss">
$blackCol: rgb(51, 51, 51);
$grayCol: rgb(207, 207, 207);
$grayOpCol: rgba(170, 169, 169, 0.664);
$whiteCol: rgb(255, 255, 255);
$permanentFont:'Permanent Marker', cursive;
$kashenFont:'Kaushan Script', cursive;
$meriendaFont: 'Merienda', cursive;
$luckiestFont: 'Luckiest Guy', cursive;
.project-comp {
  width: 260px;
  height: 210px;
  margin-bottom: 20px;
  background: $blackCol;
  margin-left: 5%;
  box-shadow: 0px 8px 24px $blackCol;
  border-radius: 5%;
  position: relative;
  &:hover{
     box-shadow: 5px 12px 24px $whiteCol;
  }
  .dis-box{
    width: 100%;
    text-align: left;
    padding-left: 2%;
    color: $whiteCol;
    overflow: hidden;
    .disc-p{
      width: 100%;
      overflow: hidden;
    }
p{
  margin-top: 2px;
  margin-bottom: 9px;
  font-family: $meriendaFont;
  font-size: 13px;

}
  }
  .img-box {
    width: 100%;
    height: 150px;
    img {
      width: 100%;
      height: 150px;
      border: 1px solid $blackCol;
    }
  }
  .view-btn {
    width: 18%;
    margin-left: 79%;
    height: 26px;
    margin-top: -30px;
    
    button {
      width: 100%;
      height: 25px;
      cursor: pointer;
      border: 1.5px solid $blackCol;
      padding-top: 3.5px;
      border-radius: 10%;
      font-family: $meriendaFont;
      font-size: 13px;
      transition: 0.4 ease-in-out;
      font-weight: bold;
      &:hover{
        
        box-shadow: 0px 2px 8px $grayCol;
        
      }
    }
  }
}
</style>
