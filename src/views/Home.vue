<template>
  <div class="home">
    <h1>We Are</h1>
    <p class="line"></p>
    <div class="our-mission">
      <!--Start First Box-->
      <div class="mission-box box1">
        <div class="mission-icon"><a href="#"><fontawesome-icon class="mission-font-icon" :icon="['fa', 'drafting-compass']"/></a></div>
        <h3>Integrated Design</h3>
        <h5>Design your dream building by expierience Engineers.</h5>
      </div>
      <!--Start secund Box-->
      <div class="mission-box box2">
        <div class="mission-icon"> <a href="#"><fontawesome-icon class="mission-font-icon" :icon="['fa', 'users']"/></a> </div>
        <h3>A Responsive Team</h3>
        <h5>A team of dedicated agents is always available .</h5>
      </div>
      <!--Start third Box-->
      <div class="mission-box box3">
        <div class="mission-icon"> <a href="#"><fontawesome-icon class="mission-font-icon" :icon="['fa', 'calendar-check']"/></a></div>
        <h3>Accuracy</h3>
        
        <h5>Accuracy in action and time .</h5>
      </div>
    </div>
    <div class="boxes">
      <h1>Our Projects</h1>
      <p class="line"></p>
    <projectBox class="onebox"
      v-for="project in projects"
      :key="project.id"
      :title="project.title"
      :discription="project.discription"
      :imgSrc="project.imgsrc"
      :location="project.location"
    />
    </div>
    <div id="view-project-box" class="view-project-box">
      <button @click="closeProjectImage" class="close-btn">X</button>
      <div class="view-img">
        <img id="big-img" :src="this.imgSrc" alt="">
      </div>
    </div>
  </div>
  
</template>

<script>
import jsonProjects from "../json/projects.json";
import projectBox from "../components/projectcomp.vue";
export default {
  name: "Home",
  components: {
    projectBox,
  },

  data: function () {
    return {
      projects: jsonProjects,
    };
  },
  methods:{
      closeProjectImage: function () {
      document.getElementById("view-project-box").style.display = "none";
    },
  },
};
</script>

<style lang="scss">
$blackCol: rgb(51, 51, 51);
$blackOpCol: rgba(51, 51, 51, 0.514);
$grayCol: rgb(207, 207, 207);
$grayOpCol: rgba(170, 169, 169, 0.664);
$whiteCol: rgb(255, 255, 255);
$orangeCol:#f8c16e;
$permanentFont:'Permanent Marker', cursive;
$kashenFont:'Kaushan Script', cursive;
$meriendaFont: 'Merienda', cursive;
$luckiestFont: 'Luckiest Guy', cursive;
.home {
  width: 100%;
  display: inline-block;
  h1 {
    margin-top: 20px;
    font-family: $luckiestFont;
    color: $blackCol;
  }
  .line{
  background: blanchedalmond;
  width: 8%;
  height: 5px;
  border-radius: 22%;
  border-top-right-radius: 100%;
  margin-left: 46%;
  margin-bottom: 50px;
}
  .boxes{
    width: 100%;
    height: 2500px;
    display: block;
    .onebox{
      transition: 0.4s ease-in-out;
      cursor: pointer;
&:hover{
  transform: translateY(10px);
  width: 280px;

}
    }
    h1{
      margin-top: 20px;
      margin-bottom: 20px;
    }
    .onebox{
      float: left;
    }
  }
  .our-mission {
    width: 95%;
    height: 400px;//470px //845px
    margin-top: 25px;
    margin-bottom: 100px;
margin-left: 4%;
    .mission-box {
      width: 300px;
      height: 210px;
      float: left;
      background: $blackCol;
      margin-left: 6.2%;
      padding-top: 30px;
      cursor: pointer;
      color: $whiteCol;
      border: 1px solid black;
      border-radius: 10%;
      box-shadow: 0px 6px 12px $whiteCol;
      margin-bottom: 50px;
          h5{
               padding-right: 2%;
    padding-left: 2%;
          font-family: $meriendaFont;
           font-size: 13px;
        }
        h3{
          font-family: $permanentFont;
          font-size: 27px;
        }
      .mission-icon {
        width: 22%;
        height: 50px;
        background: blanchedalmond;
        border-radius: 100%;
        margin-bottom: 20px;
        margin-left: 39%;
        border: 1px solid $blackCol;
        a{
          font-size: 30px;
          color:$blackOpCol;
        }
    
      }
      &:hover {
        background: $whiteCol;
        box-shadow: 0px 6px 12px $blackCol;
        opacity: 0.9;
        color: $blackCol;
        .mission-icon {
          background-color: $blackCol;
          border: 1px solid $whiteCol;
          a{
            color: $whiteCol;
          }
        }
      }
    }
    .box2 {
      margin-top: 150px;
      transition: 0.7 ease-in-out;
      &:hover {
        transform: translateY(-20px);
      }
    }
    .box1,
    .box3 {
      transition: 0.7 ease-in-out;
      &:hover {
        transform: translateY(20px);
      }
    }
  }
  .view-project-box{
    width: 100%;
    height: 1000px;
background:$blackOpCol;
z-index: 100;
top: 0;
position: fixed;
display: none;
.close-btn{
  width: 2.5%;
  height: 27px;
  position: absolute;
  right: 0;
  margin-right: 2%;
  margin-top: 10px;
  border: 1px solid $blackCol;
  border-radius: 10%;
  background: $whiteCol;
  font-family: $meriendaFont;
  transition: 0.4 ease-in-out;
  &:hover{
    width: 3%;
    font-weight: bold;
    height: 28px;
    box-shadow: 0px 2px 8px $grayCol;

  }
}
.view-img{
  width: 80%;
  height: 530px;
  margin-left: 10%;
  margin-top: 50px;
  box-shadow: 0px 4px 12px $whiteCol;
  border-radius: 5%;
  img{
    width: 100%;
    height: 530px;
     border-radius: 1%;
    
  }
}
  }
}
@media screen and (max-width: 1125px) {
  .home{
.our-mission{
  height: 780px;
  margin-left: 6%;
  width: 93%;
  .mission-box{
  float: none;
  }
  .box2{
    margin-top: 60px;
  }
}
.view-project-box {
  .close-btn {
  width: 6.5%;
  margin-right: 8%;
  &:hover{
    width: 7%;
  }
  }
  
  .view-img{
    height: 400px;
    img {
  height: 400px;
  }
}
}


.box{
  margin-left: 14%;
}
  }
}

</style>
