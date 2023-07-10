<template>

    <div class="middleData">

        <img class="currentType" src="@/assets/images/clear_sky.svg" />

        <h1 class="currentDegree">0°C</h1>
        <span class="currentCity">Undefinied</span>

    </div>

</template>

<script>
/*import ClearSky from "@/assets/images/clear_sky.svg"
import FewClouds from "@/assets/images/few_clouds.svg"
import Mist from "@/assets/images/mist.svg"
import ScatteredClouds from "@/assets/images/scattered_clouds.svg"
import ShowerRain from "@/assets/images/shower_rain.svg"
import Rain from "@/assets/images/rain.svg"
import Snow from "@/assets/images/snow.svg"
import Thunderstorm from "@/assets/images/thunderstorm.svg"
*/
export default {
    name: "MiddleData",
    methods: {
        checkWeather(data) {

            document.querySelector(".currentCity").innerHTML = data.name;
            var roundedDegree = Math.round(data.main.temp);
            document.querySelector(".currentDegree").innerHTML = roundedDegree + "°C";
            
        }
    }
}

</script>

<style>

div.middleData {

    margin-top: 8rem;
    width: 100%;
    text-align: center;

}

h1 {
    color: rgba(255, 255, 255, 0.7);
    font-size: 96px;
    margin: 0px;
}

span.currentCity {

    color: rgba(255, 255, 255, 0.7);
    font-size: 2rem;
    font-family: Inter;
    font-weight: 500;

}


</style>