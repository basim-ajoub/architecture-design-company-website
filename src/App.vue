<template>
  <div id="app">
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
    <link
      href="https://fonts.googleapis.com/css2?family=Permanent+Marker&display=swap"
      rel="stylesheet"
    />
    <link
      href="https://fonts.googleapis.com/css2?family=Kaushan+Script&display=swap"
      rel="stylesheet"
    />
    <link
      href="https://fonts.googleapis.com/css2?family=Merienda&display=swap"
      rel="stylesheet"
    />
    <link
      href="https://fonts.googleapis.com/css2?family=Luckiest+Guy&display=swap"
      rel="stylesheet"
    />
    <div id="nav">
      <div id="nav-logo">
        <div class="logo-img-div">
          <img src="ajjoub-bau-logo.png" alt="" />
        </div>
        <div class="logo-name-div">
          <h5>Ajjoub Bau</h5>
        </div>
      </div>
      <div id="nav-links">
        <router-link to="/">Home</router-link>
        <router-link to="/about">About</router-link>
      </div>
      <div id="nav-icon">
    <fontawesome-icon class="building-icon" :icon="['far', 'building']" />
      </div>
    <div id="nav-mobile-icon" >
    <fontawesome-icon id="navi-mobile-icon-close" @click="viewDropMenu" :icon="['fa', 'align-justify']" />
    <fontawesome-icon id="navi-mobile-icon-open" @click="closeDropMenu"  :icon="['fa', 'align-justify']" />
      </div>
    </div>
    <!--Start Mobile Drop Menue-->
    <div id="nav-links-mobile">
      <ul class="drop-menu-list">
     <li ><router-link to="/"><p @click="closeDropMenu"> Home</p></router-link></li> 
    <li><router-link to="/about"><p @click="closeDropMenu"> About</p></router-link></li>  
      </ul>
    </div>

    <!--Start slider image-->
    <div id="img-slider-div">
      <div id="social-box">
        <ul id="social-media-list">
          <li>
            <a href="#"
              ><fontawesome-icon
                class="socila-icon"
                :icon="['fab', 'facebook-square']"
            /></a>
          </li>

          <li>
            <a href="#"
              ><fontawesome-icon
                class="socila-icon"
                :icon="['fab', 'xing-square']"
            /></a>
          </li>
          <li>
            <a href="#"
              ><fontawesome-icon
                class="socila-icon"
                :icon="['fab', 'google-plus-square']"
            /></a>
          </li>
          <li>
            <a href="#"
              ><fontawesome-icon
                class="socila-icon"
                :icon="['fab', 'linkedin']"
            /></a>
          </li>
        </ul>
      </div>
      <div id="img-slider-box">
        <!--Satrt Image Slider -->
        <div id="image-slider">
          <img class="box-shape" :src="currentImg" alt="" />
          <div class="box-shape black-shape"></div>
          <a id="next-img-btn" class="img-btn" @click="next"
            ><fontawesome-icon :icon="['fa', 'arrow-circle-left']"
          /></a>
          <a id="prev-img-btn" class="img-btn" @click="prev"
            ><fontawesome-icon :icon="['fa', 'arrow-circle-right']"
          /></a>
        </div>
        <!--End Image Slider -->
        <div id="text-box">
          <h2 id="company-name">Ajjoub <span>Bau</span></h2>
          <h4 id="company-discription">We Design Your Dream Building</h4>
        </div>
      </div>
    </div>
    <router-view />
    <div id="footer-div">
      <p>Copyright 2021 © <span>Ajjoub Bau</span> . All rights reserved</p>
    </div>
  </div>
</template>
<script>
export default {
  name: "app",
  data() {
    return {
      imagesslider: ["back1.jpg", "back2.jpg", "back3.jpg", "back4.jpg"],
      timer: null,
      currentIndex: 0,
    };
  },
  methods: {
    viewDropMenu: function (){
      document.getElementById("nav-links-mobile").style.display= "block";
       document.getElementById("navi-mobile-icon-close").style.display= "none";
      document.getElementById("navi-mobile-icon-open").style.display= "block";
      document.getElementById("nav-mobile-icon").style.position= "fixed";
      document.getElementById("nav-mobile-icon").style.height= "45px";
    },
        closeDropMenu: function (){
      document.getElementById("nav-links-mobile").style.display= "none";
      document.getElementById("navi-mobile-icon-open").style.display= "none";
      document.getElementById("navi-mobile-icon-close").style.display= "block";
            document.getElementById("navi-mobile-icon-close").style.marginLeft= "5px";
            document.getElementById("nav-mobile-icon").style.position= "static";
      document.getElementById("nav-mobile-icon").style.height= "41px";
    },
    startSliding: function () {
      this.timer = setInterval(this.next, 8000);
    },
    next: function () {
      this.currentIndex += 1;
    },
    prev: function () {
      this.currentIndex -= 1;
    },
  },

  computed: {
    currentImg: function () {
      return this.imagesslider[
        Math.abs(this.currentIndex) % this.imagesslider.length
      ];
    },
  },
  mounted: function () {
    this.startSliding();
    document.getElementById("footer-div").style.marginTop = "auto";
  },
};
</script>
<style lang="scss">
* {
  padding: 0;
  margin: 0;
}
$blackCol: rgb(51, 51, 51);
$blackOpCol: rgba(51, 51, 51, 0.61);
$grayCol: rgb(207, 207, 207);
$grayOpCol: rgba(170, 169, 169, 0.664);
$whiteCol: rgb(255, 255, 255);
$permanentFont: "Permanent Marker", cursive;
$kashenFont: "Kaushan Script", cursive;
$meriendaFont: "Merienda", cursive;
$luckiestFont: "Luckiest Guy", cursive;
$orangeCol: #f8c16e;
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  background: $grayCol;
  #nav-links-mobile {
    width: 100%;
    height: 900px;
    background: $blackCol;
    position: absolute;
    position: fixed;
    z-index: 150;
    display: none;
    .drop-menu-list{
list-style: none;
width: 89%;
  li{
    width: 100%;
    height: 70px;
    border-bottom: 1px solid $whiteCol;
    padding-top: 20px;
    font-size: 18px;
    font-family: $meriendaFont;
    a{
      text-decoration: none;
      color: $whiteCol;
    }
    }
    }
  }
  #img-slider-div {
    background: $grayOpCol;
    width: 100%;
    height: 579px;
    display: inline-flex;
    box-shadow: 1px 1px 3px 3px $whiteCol;
    border-bottom: 2px solid $blackCol;

    #img-slider-box {
      width: 95%;
      background: $blackCol;
      border-bottom-left-radius: 30%;
      border-bottom: 2px solid $blackCol;
      border-left: 5px solid $blackCol;
      #image-slider {
        width: 94.9%;
        z-index: 2;
        height: 579px;
        position: absolute;
        border-bottom-left-radius: 29%;
        transition: all 0.9s ease-in-out;
        .box-shape {
          height: 579px;
          width: 100%;
          border-bottom-left-radius: 29.8%;
          transition: all 0.9s ease-in-out;
        }
        .black-shape {
          z-index: 4;
          background: $blackOpCol;
          opacity: 0.3;
          position: absolute;
          top: 0;
        }
        img {
          z-index: 3;
        }
        .img-btn {
          position: absolute;
          margin-top: 260px;
          color: $whiteCol;
          font-weight: bolder;
          font-size: 22px;
          cursor: pointer;
          transition: 0.4 ease-in-out;
          &:hover {
            font-size: 24px;
          }
        }
        #next-img-btn {
          left: 0.5%;
          z-index: 5;
        }
        #prev-img-btn {
          left: 97%;
          z-index: 5;
        }
      }
      #text-box {
        width: 35%;
        height: 170px;
        margin: 0px 0px 0px 63%;
        text-align: left;
        z-index: 20;
        position: relative;

        #company-name {
          height: 53px;
          font-family: $permanentFont;
          color: $blackCol;
          width: 100%;
          font-weight: bold;
          span {
            font-size: 45px;
            color: $orangeCol;
            font-family: $kashenFont;
            font-weight: bolder;
            margin: 0px;
          }
        }
        #company-discription {
          width: 100%;
          font-family: $kashenFont;
        }
      }
    }
    #social-box {
      width: 4.6%;
      overflow: hidden;
      #social-media-list {
        display: block;
        width: 100%;
        margin-top: 40px;
        list-style: none;

        text-align: center;
        margin-left: -20px;
        li {
          width: 100%;
          height: 60px;

          margin-bottom: 20px;
          cursor: pointer;
          font-size: 35px;

          a {
            color: $blackCol;

            .socila-icon {
              transition: 0.4 ease-in-out;
              &:hover {
                font-size: 33px;
                box-shadow: 0px 4px 12px $whiteCol;
              }
            }
          }
        }
      }
    }
  }
  #footer-div {
    background: $blackCol;

    width: 100%;
    height: 25px;
    padding-top: 2px;
    font-size: 14px;
    color: $grayCol;
    position: absolute;
    margin-top: auto;

    p {
      span {
        font-weight: bold;
        cursor: pointer;
      }
    }
  }
}

#nav {
  width: 100%;
  background: $blackCol;
  text-align: right;
  height: 45px;
  border-bottom: 1px solid $grayCol;
  display: inline-flex;
  a {
    font-family: $meriendaFont;
  }
  #nav-icon {
    width: 5%;
    color: $whiteCol;
    padding-top: 6px;
    text-align: center;
    font-size: 24px;
    border-left: 1px solid $whiteCol;
    cursor: progress;

  }
  #nav-mobile-icon{
    display: none;
        width: 5%;
    color: $whiteCol;
    padding-top: 6px;
    text-align: center;
    font-size: 24px;
    border-left: 1px solid $whiteCol;
    cursor: progress;
    #navi-mobile-icon-open{
      display: none;
      margin-left: 15%;
    }
  }
  #nav-links {
    width: 75%;
    height: 30px;
    padding-right: 5%;
    padding-top: 11px;
  }

  #nav-logo {
    height: 45px;
    width: 20%;

    text-align: left;
    padding-left: 0.5%;
    .logo-img-div {
      width: 24%;
      height: 45px;

      float: left;
      img {
        width: 90%;
        height: 42px;
        cursor: pointer;
      }
    }
    .logo-name-div {
      width: 95%;
      height: 45px;
      padding-top: 19px;
      cursor: pointer;
      h5 {
        font-family: $kashenFont;
        color: $orangeCol;
        font-weight: bold;
        font-size: 16px;
      }
    }
  }

  a {
    font-weight: bold;
    color: $whiteCol;
    margin-left: 3%;
    text-decoration: none;

    &.router-link-exact-active {
      // color: #42b983;
      color: $orangeCol;
    }
  }
}
@media screen and (max-width: 1000px) {
  #app {
    #nav {
      #nav-icon {
        width: 10%;
      }
      
      #nav-logo {
        width: 90%;
        .logo-img-div {
          width: 18%;
        }
      }
    }
    #social-box {
      display: none;
    }
    #img-slider-div #img-slider-box {
      width: 100%;
      #image-slider {
        width: 99%;
        #prev-img-btn {
          left: 92%;
        }
      }
      #black-shape {
        width: 99.5%;
      }
    }
    #img-slider-div {
      height: 450px;
      #img-slider-box {
        #image-slider {
          height: 450px;
          .box-shape {
            height: 445px;
            width: 99%;
          }
        }
      }
    }
  }
}
@media screen and (max-width: 600px) {
  #text-box {
    margin: 0px 0px 0px 50%;

    #company-name {
      font-size: 17px;
      span {
        font-size: 18px;
      }
    }
    #company-discription {
      font-size: 12px;
    }
  }
  #nav{
    #nav-links {
        display: none;
      }
  #nav-icon {
    position: fixed;

    right: 0;
    height: 45px;
display: none;


  }
  
  #nav-mobile-icon{
    display: block;
   
color: $whiteCol;
    right: 0;
    width: 10%;
    height: 41px;
z-index: 200;
background: $blackCol;
  }
  }
  #nav-links-mobile{

  }
}

@media screen and (max-width: 420px) {
  #app #img-slider-div #img-slider-box #text-box{
     #company-name{
    font-size: 16px;
    height: 35px;
     span{
    font-size: 22px;
  }
  }
  #company-discription{
    font-size: 12px;
  }
  }

}
</style>
