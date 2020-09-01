<template>
  <v-app>
    <v-layout column wrap justify-space-between>
          <v-flex>
      <v-toolbar dark color="white darken-1" class="hidden-xs-and-down">
          <img class="mr-3" :src="require('./assets/WeathertopiaIcon.png')" @click="goHome()" height="40" style="cursor: pointer !important"/>
          <v-toolbar-title @click="goHome()" style="cursor: pointer !important">Weathertopia</v-toolbar-title>
          <v-spacer></v-spacer>
          <v-toolbar-items>
              <v-btn
                      v-for="item in nav"
                      :key="item.icon"
                      :title="item.title"
                      :href="'/' + item.icon"
              >{{ item.text }}</v-btn>
          </v-toolbar-items>
      </v-toolbar>

      <v-toolbar dark color="blue darken-4" class="hidden-sm-and-up">
          <v-toolbar-title>Mobile Menu</v-toolbar-title>
          <v-spacer></v-spacer>

          <v-dialog v-model="dialog" fullscreen hide-overlay transition="dialog-bottom-transition">
              <v-toolbar-side-icon dark slot="activator"></v-toolbar-side-icon>
              <v-card>
                  <v-toolbar flat color="blue-grey darken-2">
                      <v-toolbar-title>Mobile Menu</v-toolbar-title>
                      <v-spacer></v-spacer>
                      <v-btn icon @click.native="dialog = false">
                          <v-icon>close</v-icon>
                      </v-btn>
                  </v-toolbar>

                  <v-list>
                      <v-list-tile
                              v-for="(item, index) in nav"
                              :key="index"
                      >
                          <v-list-tile-action>
                              <v-icon v-if="item.icon">{{item.icon}}</v-icon>
                          </v-list-tile-action>
                          <v-list-tile-content>
                              <v-list-tile-title :title="item.title">{{ item.text }}</v-list-tile-title>
                          </v-list-tile-content>
                      </v-list-tile>
                  </v-list>
              </v-card>
          </v-dialog>

      </v-toolbar>
          </v-flex>
    </v-layout>
     <v-layout column wrap justify-space-around style="height: 100%;">
          <v-flex style="display:flex;flex-direction:column">
          <router-view name="main" style="flex:1;"></router-view>    
          </v-flex>
    </v-layout>
  </v-app>
</template>

<script>

export default {
  name: 'App',
    data: function() {
        return {
            dialog: false,
            nav: [
                {
                    icon: 'home',
                    text: 'Home',
                    title: 'Are you ready to head home?',
                    active: false
                },
                {
                    icon: 'local',
                    text: 'Local',
                    title: 'Local weather information',
                    active: true
                },
                {
                    icon: 'global',
                    text: 'Global',
                    title: 'Global weather news',
                    active: false
                },
                {
                    icon: 'severe',
                    text: 'Severe',
                    title: 'Are you hearing thunder?',
                    active: false
                },
                {
                    icon: 'tropics',
                    text: 'Tropics',
                    title: 'What is brewing in the tropics?',
                    active: false
                },
                {
                    icon: 'winter',
                    text: 'Winter',
                    title: 'Is winter coming?',
                    active: false
                }
            ]
        };
    },
    methods: {
        goHome()
        {
            window.location = "/home"
        }
    }
};

</script>

<style>

    .v-btn--contained
    {
        box-shadow: none !important;
    }

    .theme--dark.v-btn:not(.v-btn--flat):not(.v-btn--text):not(.v-btn--outlined) {
        background-color: white !important;
        color: #3885BB
    }

    .v-toolbar__items
    {
        cursor: pointer;
    }

    .v-toolbar__title
    {
        color: #3885BB
    }

</style>
