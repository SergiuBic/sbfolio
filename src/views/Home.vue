<template>
 
  <div class="home">

       <v-card elevation='6' class="box">
         <v-card-title class="title-sergiu text-h5 font-weight-bold justify-center">
           Hi, I'm Sergiu. Nice to meet you!
         </v-card-title>
       <v-divider inset></v-divider>
       <v-card-text>
        I am a <b>full stack web developer</b> <span class='blue--text text--accent-3'>&amp;</span> I enjoy creating digital products!
       </v-card-text>
       </v-card>
      
      <v-card elevation="8" max-width="160px" class="mx-auto my-3 blue accent-3 px-0 py-0 box2" outlined >
      <img
        src="../assets/pic2.jpg"
        alt="SergiuBic"
        width="100%"
        height="100%"
        class="mx-auto my-0 pa-0"
      />
      </v-card>
    

  
    <v-card class="text-caption font-weight-bold my-0 box">
      <v-card-title class='justify-center'>I like to &lt; code / &gt; with:</v-card-title>

     
      <v-btn outlined class="pa-2 ma-2 box3" rounded><ion-icon name="logo-javascript" class="orange thin mr-1"></ion-icon>&nbsp;JavaScript</v-btn>
      <v-btn outlined class="pa-2 ma-2 box3" rounded><ion-icon name="logo-html5" class="green thin mr-1"></ion-icon>&nbsp;HTML/<ion-icon name="logo-css3"></ion-icon>&nbsp; CSS</v-btn>
      <v-btn outlined class="pa-2 ma-2 box3" rounded><ion-icon name="logo-python" class="yellow thin mr-1"></ion-icon>&nbsp;Python</v-btn>
      <v-btn outlined class="pa-2 ma-2 box3" rounded><ion-icon name="logo-microsoft" class="primary thin mr-1"></ion-icon>&nbsp;C# (Med)</v-btn>
      <v-btn outlined class="pa-2 ma-2 box3" rounded><ion-icon name="cafe-outline" class="blue thin mr-1"></ion-icon>&nbsp;Java (Entry)</v-btn>
  
     <v-divider class="my-2"></v-divider>
      <v-card-title class='justify-center'> Frameworks, libraries and tools:</v-card-title>
  
      <v-btn class="ma-1 box3" outlined rounded x-small><ion-icon name="logo-nodejs" class="mr-1"></ion-icon>&nbsp;NodeJS</v-btn>
      <v-btn class="ma-1 box3" outlined rounded x-small><ion-icon name="logo-vue" class="mr-1"></ion-icon>VueJS</v-btn>
      <v-btn class="ma-1 box3" outlined rounded x-small><ion-icon name="logo-vue" class="mr-1"></ion-icon>Vuetify</v-btn>
      <v-btn class="ma-1 box3" outlined rounded x-small><ion-icon name="logo-react" class="mr-1"></ion-icon>React</v-btn>
      <v-btn class="ma-1 box3" outlined rounded x-small><ion-icon name="rainy-outline" class="mr-1"></ion-icon>TailwindCSS</v-btn>
      <v-btn class="ma-1 box3" outlined rounded x-small><ion-icon name="logo-css3" class="mr-1"></ion-icon>MaterializeCSS</v-btn>
      <br/>
      <v-btn class="ma-1 box3" outlined rounded x-small><ion-icon name="analytics-outline" class="mr-1"></ion-icon>MongoDB / MySQL</v-btn>
      <v-btn class="ma-1 box3" outlined rounded x-small><ion-icon name="logo-github" class="mr-1"></ion-icon>GitHub</v-btn>
      <v-btn class="ma-1 box3" outlined rounded x-small><ion-icon name="cloud-upload-outline" class="mr-1"></ion-icon>Heroku</v-btn>
      <v-btn class="ma-1 box3" outlined rounded x-small><ion-icon name="git-network-outline" class="mr-1"></ion-icon>Netlify</v-btn>
      <v-btn class="ma-1 box3" outlined rounded x-small><ion-icon name="logo-amazon" class="mr-1"></ion-icon>AWS</v-btn>
      <v-btn class="ma-1 box3" outlined rounded x-small><ion-icon name="logo-firebase" class="mr-1"></ion-icon>Firebase</v-btn>
      <v-btn class="ma-1 box3" outlined rounded x-small><ion-icon name="logo-web-component" class="mr-1"></ion-icon>Webpack</v-btn>

   
    </v-card>
     
  </div>
</template>

<script>
import {gsap} from 'gsap';
export default {
mounted: function(){
gsap.from(".box", {
  duration: .5,
  y:-100,
  opacity: 0, 
  delay: 0.2, 
  ease: "power1", 
});

gsap.from(".box2", {
  duration: .6,
  y:-100,
  opacity: 0, 
  ease: "power2", 
});

gsap.from(".box3", {
  duration: .7,
  x:-100,
  y:-100,
  opacity: 0, 
  stagger:0.1,
  ease: "bounce", 
});
 }
}
</script>

<style scoped>
.box-shadow-please{
  box-shadow:#000000 .3px .3px .3px .3px;
}
</style>

