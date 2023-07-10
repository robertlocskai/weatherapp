<template>

    <div class="detailedData">

        <!--<div class="dataBox">
            <img id="humidity" src="@/assets/images/humidity.svg" />
            <span class="humidity">11%</span>
        </div>
        <div class="dataBox">
            Feels Like<br/>
            30°C
        </div>
        <div class="dataBox">
            <img id="windSpeed" src="@/assets/images/wind.svg" />
            <span class="windSpeed">4 MPH</span>
        </div>-->

        <table>
            <tr>
                <td>
                    <img id="humidity" src="@/assets/images/humidity.svg" />
                    <span class="humidity">0%</span>
                </td>
                <td>
                    Feels Like<br/>
                    <span class="feelDegree">0°C</span>
                </td>
                <td>
                    <img id="windSpeed" src="@/assets/images/wind.svg" />
                <span class="windSpeed">0 MPH</span>
                </td>
            </tr>
        </table>

    </div>

</template>

<script>

export default {
    name: "DetailedData",
    methods: {
        checkWeather(data) {

            document.querySelector(".humidity").innerHTML = data.main.humidity + "%";
            document.querySelector(".windSpeed").innerHTML = data.wind.speed + "MPH";
            var roundedDegree = Math.round(data.main.feels_like);
            document.querySelector(".feelDegree").innerHTML = roundedDegree + "°C";
            
        }
    }
}

</script>

<style>

div.detailedData {

    margin-top: 3rem;
    width: 100%;
    text-align: center;

}

div.dataBox {
    background-color: blue;
    display: inline-block;
    font-family: Inter;
    font-weight: 700;
    color: rgba(255, 255, 255, 0.7);
    font-size: 32px;/*
    margin-left: 2rem;
    margin-right: 2rem;*/
}

img#humidity {
    height: 2.5rem;
    vertical-align:middle;
    margin-right: 0.7rem;
}

img#windSpeed {
    margin-right: 0.7rem;
    vertical-align:middle;
}

table {
    text-align: center;
    margin-left: auto;
    margin-right: auto;
    font-family: Inter;
    font-weight: 700;
    color: rgba(255, 255, 255, 0.7);
    font-size: 32px;
}

td {
    width: 14rem;
}

</style>