<template>
 
  <div class="home" style="overflow: auto;height:100%; max-height:100%; ">

       <v-card elevation='6' class="box">
         <v-card-title class="title-sergiu text-h5 font-weight-bold justify-center">
           Hi, I'm Sergiu. Nice to meet you!
         </v-card-title>
       <v-divider inset></v-divider>
       <v-card-text>
        I am a <b>full stack web developer</b> <span class='red--text text--accent-2'>&amp;</span> I love coding/designing beautifully simple things!
       </v-card-text>
       </v-card>
  
      <v-avatar  class='my-6 box2' size="128">
      <img
        class='box-shadow-please'
        src="../assets/picturecv.jpg"
        alt="SergiuBic"
      />
    </v-avatar>
    

  
    <v-card class="text-caption font-weight-bold my-0 box">
      <v-card-title class='justify-center'>Languages that I speak:</v-card-title>

     
      <v-btn outlined class="pa-2 ma-2 box3" rounded><ion-icon name="logo-javascript" class="orange thin mr-1"></ion-icon>&nbsp;JavaScript</v-btn>
      <v-btn outlined class="pa-2 ma-2 box3" rounded><ion-icon name="logo-html5" class="green thin mr-1"></ion-icon>&nbsp;HTML/<ion-icon name="logo-css3"></ion-icon>&nbsp; CSS</v-btn>
      <v-btn outlined class="pa-2 ma-2 box3" rounded><ion-icon name="logo-python" class="yellow thin mr-1"></ion-icon>&nbsp;Python</v-btn>
      <v-btn outlined class="pa-2 ma-2 box3" rounded><ion-icon name="logo-microsoft" class="primary thin mr-1"></ion-icon>&nbsp;C#</v-btn>
      <v-btn outlined class="pa-2 ma-2 box3" rounded><ion-icon name="cafe-outline" class="red thin mr-1"></ion-icon>&nbsp;Java</v-btn>
  
     <v-divider class="my-2"></v-divider>
      <v-card-title class='justify-center'> Frameworks, libraries and tools:</v-card-title>
  
      <v-btn class="ma-1 box3" outlined rounded x-small><ion-icon name="logo-nodejs"></ion-icon>&nbsp;NodeJS</v-btn>
      <v-btn class="ma-1 box3" outlined rounded x-small><ion-icon name="logo-vue"></ion-icon>Vuetify</v-btn>
      <v-btn class="ma-1 box3" outlined rounded x-small><ion-icon name="logo-vue"></ion-icon>VueJS</v-btn>
      <br/>
      <v-btn class="ma-1 box3" outlined rounded x-small><ion-icon name="logo-react"></ion-icon>React</v-btn>
      <v-btn class="ma-1 box3" outlined rounded x-small><ion-icon name="logo-github"></ion-icon>GitHub</v-btn>
      <v-btn class="ma-1 box3" outlined rounded x-small><ion-icon name="cloud-upload-outline"></ion-icon>Heroku</v-btn>
      <v-btn class="ma-1 box3" outlined rounded x-small><ion-icon name="git-network-outline"></ion-icon>Netlify</v-btn>
      <v-btn class="ma-1 box3" outlined rounded x-small><ion-icon name="logo-amazon"></ion-icon>AWS</v-btn>
      <v-btn class="ma-1 box3" outlined rounded x-small><ion-icon name="logo-firebase"></ion-icon>Firebase</v-btn>
      <v-btn class="ma-1 box3" outlined rounded x-small><ion-icon name="logo-web-component"></ion-icon>Webpack</v-btn>

   
    </v-card>
     
  </div>
</template>

<script>
import {gsap} from 'gsap';
export default {
mounted: function(){
gsap.from(".box", {
  duration: 1.3,
  x:100,
  opacity: 0, 
  delay: 0.5, 
  ease: "power1", 
});

gsap.from(".box2", {
  duration: 1.1,
  y:100,
  opacity: 0, 
  delay: 0.5, 
  ease: "power2", 
});

gsap.from(".box3", {
  duration: 1.2,
  x:100,
  y:100,
  opacity: 0, 
  delay: 0.2, 
  stagger:0.2,
  ease: "bounce", 
});
 }
}
</script>

<style scoped>
.box-shadow-please{
  box-shadow:#000000 .3px .3px .3px .3px;
  border: 2px solid red;
}
</style>

