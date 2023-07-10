<template>

    <div class="searchBarContainer">
        <input type="text" id="searchbar" placeholder="London..." />
        <button @click="getAndSendData()">
            <img src="@/assets/images/searchIcon.svg" />
        </button>
    </div>

</template>

<script>

export default {
    name: "SearchBar",
    methods: {
        getAndSendData() {

            if(document.getElementById("searchbar").value == "") {
                this.$parent.getApiCallAndSendData("London");
            }
            else {
                var city = document.getElementById("searchbar").value;
                document.getElementById("searchbar").value = "";
                this.$parent.getApiCallAndSendData(city);
            }
        }

    }
}

</script>

<style>

div.searchBarContainer {
    width: 100%;
    text-align: center;
    margin-top: 1.5rem;
}

input#searchbar {
    outline: none;
    border: none;
    height: 4rem;
    width: 40%;
    padding-left: 1.5rem;
    padding-right: 1.5rem;
    border-radius: 5rem;
    font-size: 1.2rem;
    background-color: #191A24;
    opacity: 40%;
    color: white;
    font-family: Inter;
    font-weight: 500;
    box-shadow: rgba(0, 0, 0, 0.3) 5px 5px 10px;
    transition: 0.2s;
}

input#searchbar:hover {
    box-shadow: rgba(0, 0, 0, 0.5) 5px 5px 10px;
}

button {
    position: absolute;
    height: 4rem;
    width: 4rem;
    border-radius: 2rem;
    outline: none;
    border: none;
    background-color: rgba(0, 0, 0, 0);
    margin-top: 1px;
    transform: translateX(-100%);
    opacity: 70%;
}

button:hover {
    cursor: pointer;
}

</style>