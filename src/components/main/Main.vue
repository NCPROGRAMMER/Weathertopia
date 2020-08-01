<template>
  <v-layout row justify-center>
    <v-toolbar dark color="blue darken-4" class="hidden-xs-and-down">
      <img class="mr-3" :src="require('../../assets/WeathertopiaIcon.png')" height="40"/>
      <v-toolbar-title>Weathertopia</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-toolbar-items>
        <v-btn
                v-for="item in nav"
                :key="item.icon"
                to="#"
                :title="item.title"
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
                    to="#"
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

    <v-container fluid>
      <v-slide-y-transition mode="out-in">
        <v-layout column align-center>
          <h1 class="display-1">Welcome to Weathertopia</h1>
          <p>

          </p>
        </v-layout>
      </v-slide-y-transition>
    </v-container>
  </v-layout>
</template>

<script>
  export default {
    name: 'Main',

    data(){
      return {
        dialog: false,
        nav: [
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
          },
          {
            icon: 'prediction',
            text: 'Predictions',
            title: 'Let\'s take a peak into the future',
            active: false
          }
        ]
      }
    },
  }
</script>

<style>

  .v-btn--contained
  {
    box-shadow: none !important;
  }

  .theme--dark.v-btn:not(.v-btn--flat):not(.v-btn--text):not(.v-btn--outlined) {
    background-color: #0D47A1 !important
  }

  .v-toolbar__items
  {
    cursor: pointer;
  }

</style>
