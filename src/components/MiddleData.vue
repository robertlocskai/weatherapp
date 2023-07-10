<template>

    <div class="middleData">

        <img class="currentType" src="@/assets/images/clear_sky.svg" />

        <h1 class="currentDegree">0°C</h1>
        <span class="currentCity">Undefinied</span>

    </div>

</template>

<script>

export default {
    name: "MiddleData",
    methods: {
        checkWeather(data) {

            document.querySelector(".currentCity").innerHTML = data.name;
            var roundedDegree = Math.round(data.main.temp);
            document.querySelector(".currentDegree").innerHTML = roundedDegree + "°C";
            console.log(data);
            if(data.weather[0].main == "Clouds") {
                document.querySelector(".currentType").src = this.getImgUrl("scattered_clouds");
            }
            else if(data.weather[0].main == "Clear") {
                document.querySelector(".currentType").src = this.getImgUrl("clear_sky");
            }   
            else if(data.weather[0].main == "Snow") {
                document.querySelector(".currentType").src = this.getImgUrl("snow");
            }
            else if(data.weather[0].main == "Rain") {
                document.querySelector(".currentType").src = this.getImgUrl("rain");
            }   
            else if(data.weather[0].main == "Thunderstorm") {
                document.querySelector(".currentType").src = this.getImgUrl("thunderstorm");
            }

        },
        getImgUrl(data) {
            return require("@/assets/images/" + data + ".svg")
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