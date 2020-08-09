<template>
    <v-container fluid>
            <v-slide-y-transition mode="out-in">
                <v-layout column align-center>
                    <h1 class="display-1">NOAA GOES-East Satellite</h1>
                    <div>
                    <iframe src="https://www.star.nesdis.noaa.gov/GOES/conus_band.php?sat=G16&band=GEOCOLOR&length=12&output=embed" height="500px" width="700px"></iframe>
                    </div>
                    <p>

                    </p>
                </v-layout>
            </v-slide-y-transition>
        </v-container>
</template>

<script>
    export default {
        name: 'Tropics',
    }
</script>

<style>

</style>
