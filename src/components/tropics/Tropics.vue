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
/*
    var xmlhttp, xmlDoc;
    xmlhttp = new XMLHttpRequest();
    xmlhttp.open("GET", "http://www.nhc.noaa.gov/gis/kml/nhc_active.kml", false);
    xmlhttp.send();
    xmlDoc = xmlhttp.responseXML;

    var z = xmlDoc.getElementsByTagName("Folder");
    for (var k = 0; k < z.length; k++) {
        var x = z[k].childNodes;
        for (var i = 0; i < x.length; i++) {
            var y = x[i];
            if (y.nodeType == 1) {
                document.write(y.nodeName + ":" + y.firstChild.nodeValue + "<br />");
            }
        }
        document.write("-------------------<br/>");
    }
    */

    export default {
        name: 'Tropics',
    }



</script>

<style>

</style>
