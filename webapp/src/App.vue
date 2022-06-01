<template>
  <v-app> 
  <v-card>  
    <v-navigation-drawer app
      v-model="drawer"
      :mini-variant.sync="mini"
      permanent
      class="verticalNavBar"
      
    >
      <v-list-item class="md-12">
        <v-list-item-avatar>
          <v-img src="https://randomuser.me/api/portraits/men/85.jpg"></v-img>
        </v-list-item-avatar>

        <v-list-item-title>John Assey</v-list-item-title>

        <v-btn
          icon
          @click.stop="mini = !mini"
        >
          <v-icon>mdi-chevron-left</v-icon>
        </v-btn>
      </v-list-item>

      <v-divider></v-divider>

      <v-list dense>
        <v-list-item
          v-for="item in items"
          :key="item.title"
          link
        >
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
  </v-card>

    <v-main class="main">    
      <CalendarScheduler/> 

    </v-main>
  </v-app>
</template>

<script>
import CalendarScheduler from './components/CalendarScheduler.vue'


export default {
  name: 'App',

  components: {
    CalendarScheduler
    
  },

     data () {
      return {
        drawer: true,
        items: [
          { title: 'Home', icon: 'mdi-home-city' },
          { title: 'My Account', icon: 'mdi-account' },
          { title: 'Users', icon: 'mdi-account-group-outline' },
        ],
        mini: true,
      }
    },

};
</script>

<style scoped>

        #app {
          background-color: #E5E5E5;
          padding: 10px;
          
        }

         nav {
            /* Vertical Navbar 2 */

            /* Auto layout */

            display: flex;
            flex-direction: column;
            align-items: center;
            padding: 24px;
            gap: 24px;
            margin: 10px;

            
            min-width: 94px;
            height: 67px;

            background: #FFFFFF;
            border-radius: 6px;
            border-color: #FFFFFF;;
            border-width: 1px;
            border-style: solid;
         }

         .main {
           padding: 10px;
           height: 95%;

         }

         .verticalNavBar {
           height: 95% !important;
           top: 0px;
           max-height: calc(100% - 0px);
           transform: translateX(0%);
           width: 56px;
         }

         .v-navigation-drawer--open {
           margin-right: 10px !important;
         }
</style>
