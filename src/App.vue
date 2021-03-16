<template>
<v-app >
<v-main>
  <div class="portrait" v-show="portrait">
<div class="phone text--red text--acent-2" >
</div>
<div class="message red--text text--accent-2">
  Please rotate your device!
</div>
</div>
 <v-card outlined class="rounded-0 grey darken-4 white--text diagonal-container-0 " v-show="landscape||desktop">
   <v-avatar max-width='180px' width="180px" class="redressed mx-0 my-0 py-6 px-0 d-block logo-title red--text text--accent-2"><a href="/" id="sergiu-text-gsap"></a></v-avatar>
 <v-card outlined  class="my-0 d-flex fex-row rounded-0 red accent-2 white--text diagonal-container" height="100%" max-width="100%" >

<v-row style="flex-wrap: nowrap;" align="center" justify="center" class="mx-0 my-0 py-0 px-0 row-content"> 
 <v-col
   cols="1"
   :style="toggleActive ? `${item.active ? `${item.minwidth} height:100%; max-height:100%;`:'min-width:10%;max-height:100%;height:100%;overflow:hidden;'}` : 'min-width:25%; height:100%; max-height:100%;'"
   class="mx-0 my-0 px-0 py-0 menu-content"
   :class="item.active ? item.style : ''"
   v-for="(item,index) in links" 
   :key="index" 
  @click="toggleItem(item)"
  >
  <v-card
   class="red accent-2 white--text mx-0 my-0 py-0 px-0"
   width="100%"
   :style="toggleActive ? `${item.active? 'height:100%;' : 'height:100vh;'}`:'height: 100%;'"
   outlined
   tile
   :class="toggleActive ? `${item.active ? 'text-h6':'vertical-text text-subtitle-2'}`:''"
  >
  <v-card-actions class="mx-0 my-0 py-0 px-0" style="height: 100%; width:100%"><v-btn elevation="0" :class="toggleActive ? `${item.active ? 'text-h6' : 'text-subtitle-2'}` : 'text-h4'" class="pa-2 red accent-2 black--text mx-0 my-0 font-weight-bold" :to="item.to"  style="height: 100%;" width="100%">{{item.title}}</v-btn></v-card-actions>
  </v-card>
 </v-col>
 <v-col  min-width="20%" cols="1" :class="toggleActive ? 'flex-grow-1 flex-shrink-0 ':'flex-grow-0 flex-shrink-1 '" class=" mx-0 my-0 px-0 py-0" style="height: 100%;" :style="toggleActive ? 'min-width:55%;max-width:100%': 'display: none !important;'" >
   
   <v-card style="height: 100%;" justify="center" align="center" class="rounded-0 font-weight-bold text-body2 view-container"> 
    <router-view></router-view>

   </v-card>
 </v-col>
</v-row>


 </v-card>
 </v-card>
 </v-main>

</v-app>
</template>
<script>
import {gsap} from 'gsap';
import {TextPlugin} from 'gsap/TextPlugin.js';
gsap.registerPlugin(TextPlugin);
export default({
  data(){
    return{
      portrait: false,
      landscape:false,
      desktop: false,
      toggleActive: false,
      minwidth: "min-width: 20%;",
      links: [
        {to: "/", title:"About", active:false,style:"flex-grow-0 flex-shrink-1", closedStyle:"vertical-text", minwidth:"min-width: 35%;"},
        {to: "/projects", title:"Work",active:false,style:"flex-grow-0 flex-shrink-1",closedStyle:"vertical-text", minwidth:"min-width: 35%;"},
        {to: "/contact", title:"Contact",active:false,style:"flex-grow-0 flex-shrink-1",closedStyle:"vertical-text", minwidth:"min-width: 35%;"},
      
      ]
    }
  },
  mounted: function(){
     window.addEventListener(
      "orientationchange",
      this.handleOrientationChange
    );
    this.handleOrientationChange();

    gsap.from(".diagonal-container",{scaleY:0,duration:1.5,delay:0.1})
    gsap.to("#sergiu-text-gsap", {text: {value: "Sergiu Bîc"}, duration: 3, delay: 1, ease: "none"})
  },
 methods: {
   handleOrientationChange() {
      const ua = navigator.userAgent;
      const orientation = window.screen.orientation.type
      console.log("yolo")
  if (/(tablet|ipad|playbook|silk)|(android(?!.*mobi))/i.test(ua)  || /Mobile|iP(hone|od)|Android|BlackBerry|IEMobile|Kindle|Silk-Accelerated|(hpw|web)OS|Opera M(obi|ini)/.test(
    ua
    )) 
  {
    //tablet - phone
      if (orientation === "portrait-primary") {
        
        console.log("portrait")
             this.portrait = true
             this.landscape = false
             this.desktop = false
        } else if (orientation === "landscape-primary") {
          console.log("landscape")
          this.landscape = true
             this.portrait = false
             this.desktop = true
      }
  }
  else{
    //desktop
    console.log("desktop")
    this.desktop = true;
    this.landscape = false;
    this.portrait = false;
  }
    
    },
   toggleItem : function(item){
     for (let index = 0; index < this.links.length; index++) {
       const element = this.links[index];
       element.active = false
       element.style = "flex-grow-0 flex-shrink-1"
     }
  
     item.active = !item.active
     item.style = "flex-grow-1 flex-shrink-0 order-first"
     this.toggleActive = true
   },

  }
})
</script>

<style lang="scss">
div.v-application {
  font-family: 'Nunito', sans-serif !important;
  
}
div.v-application .text-h2 {
  font-family: 'Nunito', sans-serif !important;
}
body {
  background-color:#212121;
  margin: 0;
  padding: 0;
}
#app {
  text-align: center;
  color: #212121;
  margin:0;
  padding:0;

 
}
.diagonal-container-0 {
  height: 100%;
  width: 100%;
  
}

.diagonal-container {
  margin-top:4%;
  padding:0;
  height:80%;
  max-height: 87%;
  width: 100%;
  max-width:100%;
  transform: skewY(-3deg);
  
  
}
.container-group{
  margin:0;
  padding:0 !important;
  width:100%;
  height:inherit !important;


}
.logo-title{
  transform: skewY(-3deg);
  font-size:1.3rem;
  font-weight:italic;
}
.logo-title a{
  text-decoration: none;
  color:inherit;
  background-color:inherit;
}
.logo-title a:active{
  text-decoration: none;
  color:inherit;
  background-color:inherit;
}
.logo-title a:visited{
  text-decoration: none;
  color:inherit;
  background-color:inherit;
}
.redressed {
  font-family: 'Redressed', cursive;
}
.vertical-text {
  writing-mode:tb;
  text-orientation: upright;

}

.menu-content{
  transition: 1s ease-in-out;
}
.view-container{
  transition: 1s ease-in-out;
}
.portrait{
  height:100%;
  width:100%;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  background-color:#212121;

}
.phone {
  height: 50px;
  width: 100px;
  border: 3px solid red;
  border-radius: 10px;
  animation: rotate 1.5s ease-in-out infinite alternate;
  /* display: none; */
}

.message {
  
  font-size: 1em;
  margin-top: 40px;
  /* display: none; */
}

@keyframes rotate {
  0% {
		transform: rotate(0deg)
	}
	50% {
		transform: rotate(-90deg)
	}
	100% {
		transform: rotate(-90deg)
	}
}

@media only screen and (max-device-width: 812px) and (orientation: landscape) {
  .phone, .message {
    display: block;
  }
}
</style>
