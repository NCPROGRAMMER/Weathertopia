<template>
      <div class="background-image" :style="{ backgroundImage: 'url(' + require('@/assets/bg1.jpg') + ')'}" style="display: flex;
  align-items: center;">
      <v-slide-y-transition mode="out-in">
        <v-layout column align-center>
          <h1 class="display-1" style="margin-top: 1%; color: white">Welcome to Weathertopia</h1>
          <v-container class="grey lighten-5"  style="background-color: transparent !important;">
      <v-row>
        <v-col class="image-column" v-for="item in img" :key="item.icon" lg="4" md="6" sm="12" @click="redirect(item.path)" style="padding-bottom: 10px;text-align: center">
          <img :src="require('../../assets/' + item.path + '.jpg')" :href="'/' + item.path" width="350" height="350" />
          <figcaption style="color: white">{{ item.title }}</figcaption>
        </v-col>
      </v-row>
    </v-container>
        </v-layout>
      </v-slide-y-transition>
      </div>
</template>

<script>

  export default {
    name: 'Main',
    data: function() {
        return {
            dialog: false,
            img: [
                {
                    path: 'local',
                    text: 'Local',
                    title: 'Local weather information',
                    active: true
                },
                {
                    path: 'global',
                    text: 'Global',
                    title: 'Global weather news',
                    active: false
                },
                {
                    path: 'severe',
                    text: 'Severe',
                    title: 'Are you hearing thunder?',
                    active: false
                },
                {
                    path: 'tropics',
                    text: 'Tropics',
                    title: 'What is brewing in the tropics?',
                    active: false
                },
                {
                    path: 'winter',
                    text: 'Winter',
                    title: 'Is winter coming?',
                    active: false
                }
            ]
        };
    },
    methods: {
        redirect(path)
        {
            window.location = "/" + path;
        }
    }
  }
</script>

<style>

.image-column
{

cursor: pointer !important;

}

.background-image
{

  background-position: center;
  background-repeat: no-repeat;
  background-size: 100% 100%;

}

html 
{ 
  
  overflow-y: auto;

}


</style>
