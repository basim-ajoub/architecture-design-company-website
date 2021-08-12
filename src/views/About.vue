<template>
  <div class="about">
    <h1>About Us</h1>
    <div class="about-content">
  <div id="about-info">
         <h2>Contact</h2>
         <p class="line"></p>
         <ul class="contact-list">
         <li ><fontawesome-icon class="contact-icon" :icon="['fas', 'map-marker-alt']"/>Pascal straße - Berlin - Deutschland .</li> 
         <li ><fontawesome-icon class="contact-icon" :icon="['fas', 'phone']"/>041-12542548 .</li>
         <li ><fontawesome-icon class="contact-icon" :icon="['fas', 'envelope']"/>archdesign@gmail.com .</li>
         </ul>
         <h2>We Are Social</h2>
         <p class="line"></p>
         <ul class="socail-list">
           <li> <a href="#"><fontawesome-icon class="socila-icon" :icon="['fab', 'facebook-square']"/></a></li>
           <li><a href="#"><fontawesome-icon class="socila-icon" :icon="['fab', 'xing-square']" /></a></li>
           <li><a href="#"><fontawesome-icon class="socila-icon" :icon="['fab', 'google-plus-square']"/></a></li>
           <li><a href="#"><fontawesome-icon class="socila-icon" :icon="['fab', 'linkedin']" /></a></li>
         </ul>
         
    </div>
 
    <div id="about-map">
      <h2>We Are Here</h2>
      <p class="line"></p>
      <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d2427.6030889008975!2d13.322419015244826!3d52.522521743795565!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x47a85110d8056baf%3A0x6bed639f5c47eb12!2sPascalstra%C3%9Fe%2C%2010587%20Berlin%2C%20Germany!5e0!3m2!1sen!2s!4v1627380349907!5m2!1sen!2s" width="70%" height="300" style="border:0;" allowfullscreen="" loading="lazy"></iframe>
    </div>
    </div>
  
  </div>
</template>
<style lang="scss">
$blackCol: rgb(51, 51, 51);
$grayCol: rgb(207, 207, 207);
$grayOpCol: rgba(170, 169, 169, 0.664);
$whiteCol: rgb(255, 255, 255);
$permanentFont:'Permanent Marker', cursive;
$kashenFont:'Kaushan Script', cursive;
$meriendaFont: 'Merienda', cursive;
$luckiestFont: 'Luckiest Guy', cursive;
.about{
  width: 100%;
  margin-top: 30px;
h1{
  font-family: $luckiestFont;
  color: $blackCol;
}
h2{
  font-family: $permanentFont;
  font-weight: 10px;
  color: $blackCol;
}
  .about-content{
  display: inline-flex;
  width: 100%;
 
  margin-top: 40px;
 .line{
  background: blanchedalmond;
  width: 15%;
  height: 5px;
  border-radius: 22%;
  border-top-right-radius: 100%;
  margin-bottom: 20px;
}
  #about-map{
    width: 50%;
    text-align: left;
    margin-bottom: 20px;
    h2{
      margin-top: 10px;
    }
    .line{
      margin-top: 10px;
    margin-bottom: 20px;

    }
  }
  #about-info{
    width: 50%;
    text-align: left;
    padding-left: 4%; font-family: $meriendaFont;
    .contact-list{
      list-style: none;
    margin-bottom: 30px;
      li{
        margin-bottom: 15px;
        .contact-icon{
          font-size: 20px;
          margin-right: 2%;
          color: $blackCol;
         
        }
      }
    }
     
    h2{
      margin-bottom: 10px;
      margin-top: 20px;
      
    }
    .socail-list{
      display: inline-flex;
      list-style: none;
      width: 100%;
      margin-top: 5px;
      li{
        width: 7%;
    height: 40px;
    transition: 0.6 ease-in-out;
    border-radius: 100%;
    margin-right: 2%;
    &:hover{
      background: $whiteCol;
    }
        text-align: center;
        a{
          color: $blackCol;
        }
        .socila-icon{
          font-size: 30px;
         margin-top: 5px;
         
        }
      }
    }
  }
}

}
@media screen and (max-width:800px){
  .about{
    .about-content{
      display: block;
      #about-info{
        width: 100%;
      }
      #about-map{
        margin-bottom: 0px;
            width: 96%;
    margin-left: 4%;
      }
    }
  } 
}
</style>