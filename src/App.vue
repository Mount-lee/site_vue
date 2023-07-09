<script >
import axios from 'axios'

export default {
  data () {
    return {
      city: "",
      error: "",
      info: null
    }
  },
  methods: {
    getWeather() {
      if(this.city.trim().length < 2) {
        this.error = alert("Введите корректный город")
        return false
      }

      axios.get(`https://api.openweathermap.org/data/2.5/weather?q=${this.city}&units=metric&appid=ea4220539ab1bde61db6c54135c6942b`)
          .then(res => (this.info = res))
    }
  }
}


</script>

<template>
<div id="currency">
      <h5><a href="/src/currency.html">Конвертер валют</a></h5>
    </div>
    <div id="wrapper">
      <h1>Прогноз погоды в городе {{city == "" ? "..." : "*" + city + "*"}}</h1>
      <p>Укажите город </p>
      </div>
      <div id="mainly">
      <form>
        <input type="text" v-model="city"  placeholder="Введите город">
        <button id="btn_gradient" v-if="city != ''" @click="getWeather()"> Поиск </button>
        <button id="btn_gradient" disabled v-else> Поиск </button>
      </form>
      <p v-show="info != null">{{ info }}</p>
      </div>
</template>

<style scoped>

</style>
