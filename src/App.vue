<template>
<v-app>
 <v-navigation-drawer
      v-model="drawer"
      class="blue accent-3 white--text"
      app
      right
      disable-route-watcher
      disable-resize-watcher
      temporary
    >
         <v-list-item>
        <v-list-item-content>
          <v-list-item-title class="redressive">
            SB
          </v-list-item-title>
  
        </v-list-item-content>
      </v-list-item>

      <v-divider></v-divider>
      <v-list
        dense
        nav
      >
        <v-list-item
          v-for="(item,index) in links"
          :key="index"
          :to="item.to"
          link
          class='font-weight-bold white--text'
        >

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
  
    <v-app-bar app  class="blue accent-3 white--text"
  dense>
      <v-toolbar-title class='redressive' style="overflow: inherit;">
       Sergiu Bîc
      </v-toolbar-title>
      <v-spacer></v-spacer>
       <v-tabs right color="white">
    <v-tab v-for="(item,index) in links" :key="index" link :to="item.to" class="font-weight-bold white--text hidden-sm-and-down">{{item.title}}</v-tab>
  </v-tabs>
 
         <v-app-bar-nav-icon @click="drawer = !drawer" class="hidden-md-and-up"></v-app-bar-nav-icon>
    </v-app-bar>

<v-main>
    <router-view></router-view>
 </v-main>

</v-app>
</template>
<script>

export default({
  data(){
    return{
      drawer: false,
      right:true,
      links: [
        {to: "/", title:"About", active:true},
        {to: "/projects", title:"Work",active:false},
        {to: "/contact", title:"Contact",active:false},
      
      ]
    }
  },

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


.logo-title{
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
.redressive {
  font-family: 'blueressed', cursive;
}

.menu-content{
  transition: 1s ease-in-out;
}
.view-container{
  transition: 1s ease-in-out;
}

</style>
