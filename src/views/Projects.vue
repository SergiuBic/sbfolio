<template>
<v-container fluid>
  
<v-tabs slider-color="blue" grow show-arrows :vertical="$vuetify.breakpoint.mdAndUp">
      <v-tab v-for="project in projects" :key="project.id">
        {{project.name}}
      </v-tab>

      <v-tab-item v-for="project in projects" :key="project.id">
        <v-card flat class="mx-auto justify-center">
          <v-card-title class="mx-auto justify-center">
            {{project.title}}
          </v-card-title>
       
          <v-card-actions class="mx-auto justify-center">
            <v-btn class="primary" rounded :href="project.to"  target="_blank">Go to {{project.name}}</v-btn>
          </v-card-actions>
          <v-card-text class="mx-auto justify-center">
           <p class="mx-auto justify-center font-weight-bold" v-for="(item,index) in project.content" :key="index">{{item}}</p>
          </v-card-text>
        </v-card>
      </v-tab-item>
</v-tabs>



</v-container>
</template>

<script>
export default {
  data(){return{
   projects : [
       {id:11, name: "Discuter", to: "https://discuter-sergiubic.netlify.app", img:"../assets/slavicivue.jpg", title: "Full Stack Chat App (Firebase/ReactJS)", 
     content: ["A simple chat app made with ReactJS while the back end is powered by Firebase, thanks Google!",
     "After you see it and try it you might say: Well... nothing fancy, what's this ?",
     "The idea behind was to learn code architecture and design patterns.",
     "Yeah, I've learned so much about how to structure the project, how to 'not use Redux' and how to wrap things in the app context",
     "Believe me, avoiding 'prop drilling' by using a well structured project along with a good design pattern is a life changer",
     "I have anything from the back-end ready in just one place. The workflow was very smooth as it took only 1 week.",
     "I've also learned NoSQL which I've always been curious: how this thing work and why people prefer it over SQL ?!",
     "My ReactJS learning path is getting stronger and stronger and I'm so grateful!",
     "You might say that the styling/CSS isn't a big deal, and that's completly true, but the gathered knowledge by using Styled-Components is something fancy for me.",
     "Learn by doing things, good or bad :)",
     "Cheers!",
      " ",
      " ",
      " ",
      " ",
      "P.S.: True story, a friend of mine told me: Why you never change the Title or the Favicon?! Why?",
      "Hey friend, thanks for the feedback! :)",
      " ",
      " ",
      "Disclaimer: This repo is private due to the awesome work. Please reach me to become a collaborator."],
       },

     {id:1, name: "Lumea Lui Alice", to: "https://lumealuialice.herokuapp.com", img:"../assets/lumealuialice.jpg", title: "Full Stack eCommerce", 
     content: ["This one was made with love! As my wife's hobby is to create cool hand-painted baby clothes, I grabbed my cup of coffee and started to sketch this idea on the paper.",
     "It was such a journey but my goal was to NOT use any front-end JS/CSS framework. Yeah, that's true, this website is made without any front-end modern tech. After finishing it, everything seems more clear to me. How did the Views work ? API's ? Fetching?! Wow, I now kinda understand how the modern techs like React/Vue works and why people use them so much. To not overkill this process. I've learned so many things!",
     "Mostly, I've used NodeJS with Express along with the lovely MongoDB life changer. For the Front end, everything is 'vanilla' but not Ice baby, just vanilla, vanilla! "]
     },
     
     {id:2, name: "Team Manager", to: "https://tm-sergiubic.netlify.app", img:"../assets/slavicivue.jpg", title: "Front End ReactJS/TailwindCSS/DaisyUI", 
     content: ["Feeling more comfortable with the ReactJS's workflow.", "With the idea that every leader should have an overview for his team, I've created the Team Manager app.","During the process, I've used DaisyUI which is build on top of the TailwindCSS library. Awesome!","Reusable components, States, Props, Refs and Effects are no longer the unknown, which is great and very cool!","The app can scale so much from now on but I'll stop on this version so I can build another cool stuff, maybe later! :)"],
 
     },
     {id:3, name: "SlaviciCenei rework VueJS", to: "https://slavicicenei.netlify.app", img:"../assets/slavicivue.jpg", title: "Front End VueJS/Vuetify", 
     content: ["As I'm developing my Vue/Vuetify skills, I just find some spare time to re-work the vanilla website into a more cool and up-to-date responsive product.","Nothing fancy here, but I've learned some SEO principles and did you know that even the color matters ?",
     "Fo' real! I did some research and I've used that praticular yellow as it's reflecting the client's main domain of work. It's crazy!",
     "Also, on this project we're fetching data from a Heroku API - Google Sheets API, with just JS it's alright but with VueJS it's PERFECT! Literally, perfect."],
 
     },
     {id:4, name: "SlaviciCenei Vanilla", to: "https://slavicicenei.ro", img:"../assets/slaviciceneivanilla.jpg", title: "Front End JS/MaterializeCSS", 
     content: ["Happy customer, Happy Life !",
     "First step? Customer research obviously!",
     "The customer main work domain is mixed but focused on industrial wood thingy. Ok ok, so good so far, but how can we mix the others ?",
     "I found the MaterializeCSS the best choice here as it's like a Marvel hero for mixed things while other frameworks seem overused for me. Just my opinion.",
     "On this project, I've learned lots of things about design responsiveness, git pages and how to properly set-up a Domain Name, a DNS etc."]
     },
     {id:5, name: "EM's", to: "https://play.google.com/store/apps/details?id=com.BLENCStudio.Ems&amp;hl=en&amp;gl=US", img:"../assets/ems.jpg", title: "Unity3D/C# Arcade Game", 
     content: ["My gift for my daughter.",
     "On this time, my daughter wasn't yet on this world, and as a future father then, I've thought 'ok, why not? She'll love it one day!'",
     "Everything was new to me: scripting language, platform, 3D stuff?!, lighting?! We need more coffee!",
     "It was a 1 month project. First week: youtube tutorials on how to draw a butterfly. Huh", 
     "Second week: Learning Unity3D from Udemy and then creating the blueprints",
     "Third week: Bugs bugs, and optimizations",
     "Last week: Testing, like literally hours and hours of testing and fixing/ adding new features",
     "Then I just launch it. Do you know what ? NOW the real developing starts! I've spend another month optimizing, advertising, re-sketching, re-programing etc.",
     "It was my favourite journey into the unknown!"]
     },
    {id:6, name: "Declaration on own responsability", to: "https://sergiubic-dpr.netlify.app", img:"../assets/reactsimple.jpg", title: "Front End ReactJS", 
     content: ["With tiny steps, I learn and develop my ReactJS skills!","Currently the app works only on Desktop/Laptop devices and it will generate a declaration in the romanian language very quickly. Thanks React!",
     "The workflow was relatively easy. I will definately update it for a better performance. Also TailwindCSS was kind of handy.",
     "It was just a side idea which came into my mind and I felt like it must be part of my learning react path.","I learn by doing things, good or bad, doesn't matter.",
     "Cheers :)"],
     },
     {id:7, name: "IncognitoDesign", to: "https://slavicicenei.ro/IncognitoDesign", img:"../assets/IncognitoDesign.jpg", title: "Front End JS/MaterializeCSS", 
     content: ["Great case study with another happy customer!",
     "On this project I've discovered the CSS frameworks and their divine power.",
     "Yes, I've tried like 4 frameworks before decided to finish it with MaterializeCSS",
     "The main idea was simple: Custom furniture portofolio",
     "I've used my previous knwoledge to get this SEO right, along with the colors, logo and other stuff."]
     },
    {id:8, name: "Simple To Do List", to: "https://sergiubic.github.io/ReactSimpleToDo", img:"../assets/reactsimple.jpg", title: "Front End ReactJS", 
     content: ["While learning ReactJS, I did what all the great developers do: a to do list.",
     "Please ignore the CSS as the main purpose was to understand states & props. Mostly, how this thing works ?",
     "This tiny library is awesome!!"]
     },
     {id:9, name: "HappySwing", to: "https://play.google.com/store/apps/details?id=com.BLENCStudio.HappySwing&amp;hl=en&amp;gl=US", img:"../assets/happyswing.jpg", title: "Unity3D/C# Endless Game", 
     content: ["After creating Em's, I couldn't stop!",
     "I knew that I can do this thing again without any assitance and I did !",
     "So I've bought some pre-made assets to make it look more cooler. My 3D modeling skills kinda suck..",
     "But this time was different, this time I get deeper into the C# language and learned the best practices for the best FPS and optimizations.",
     "This time, the game developing experience was friendly and I've took down the unknown."]
     },
     {id:10, name: "My Portofolio", to: "#", img:"", title: "Front End VueJS/Vuetify", 
     content: ["Well, nowadays every web developer must have a portofolio.",
     "Coffee check, VueJS check, Vuetify check, Cool blue theme check, Firebase ? Maybe later!",
     "Just exploring Vuetify here and it's cool features.",
     "If you have any ideas or feedback, please reach me via the Contact form!"]},

   ]
  }},
}
</script>
