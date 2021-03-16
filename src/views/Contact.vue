<template>
  <div class="contact" style="overflow: auto; max-heigth:100%; height:100%;">

<div class='justify-center pt-3'>
<h1 class="box">Thanks for reaching out !</h1>
<h4 class="box2">Let's get in touch : </h4>
<v-card elevation="2" max-width="50%">
<v-form
  action="https://formspree.io/f/xvovelvk"
  method="POST"
  class='d-flex flex-column justify-center pa-4 box3'
>
<v-text-field
      label="Your e-mail"
      name="_replyto"
      class="box3"
    ></v-text-field>
    <v-text-field
      name="message"
      label="Your message:"
      class='box3'
      
    ></v-text-field>
 

  <v-btn class="success box2" type="submit">Send</v-btn>
</v-form>
</v-card>
<v-divider class="my-5 box"></v-divider>
<v-card class="justify-center pa-4 box" elevation="5" max-width="50%">
<v-card-subtitle class="text-body-2 font-weight-bold justify-center box2">Or, let's get social:</v-card-subtitle>
<v-btn target="_blank" href="https://www.linkedin.com/in/sergiubic/" rounded outlined class="box3 blue-grey--text mx-2"><ion-icon name='logo-linkedin'></ion-icon></v-btn>
<v-btn target="_blank" href="https://github.com/sergiubic" rounded outlined class="box3 black--text mx-2"><ion-icon name='logo-github'></ion-icon></v-btn>
<v-btn target="_blank" href="https://www.facebook.com/wikinn/" rounded outlined class="box3 blue--text mx-2"><ion-icon name='logo-facebook'></ion-icon></v-btn>
<v-btn target="_blank" href="https://www.instagram.com/wikinsergiu/" rounded outlined class="box3 purple--text mx-2"><ion-icon name='logo-instagram'></ion-icon></v-btn>
</v-card>
</div>
  </div>
</template>


<script>
import {gsap} from 'gsap';
export default {
mounted: function(){
gsap.from(".box", {
  duration: 1,
  x:100,
  opacity: 0, 
  delay: 0, 
  stagger:0.2,
  ease: "power1", 
});

gsap.from(".box2", {
  duration: 1,
  y:100,
  opacity: 0, 
  delay: 0.1, 
  stagger:0.1,
  ease: "power2", 
});

gsap.from(".box3", {
  duration: .7,
  x:100,
  y:100,
  opacity: 0, 
  delay: 0.1, 
  stagger:0.1,
  ease: "bounce", 
});
 }
}
</script>

<style scoped>

</style>

