<template>
  <div>
    <form class="form">
      <div class="weather__top">
        <select class="select__city" v-model="weatherList"> Бажано не створювати великих компонентів. Краще розбивати на більш маленькі
          <option v-for="weather in weatherListData" :key="weather.id"
                  :value="weather.city"> {{weather.city}}</option>
        </select>
        <div class="weather__top__time">{{ todayTime }}</div>
      </div>
      <div class="container">
        <div
        class="weather__in__city"
        v-for="weather in filteredWeatherListData"
        :key="weather.id"
      >
        <div class="weather__temp">
          <img class="term__img" :src="weather.termImg" />
          <div class="temprature">{{ weather.temp }}</div>
        </div>
        <div class="weather__param">
          <div class="humidity">
            <span>Вологість:</span> {{ weather.humid }}
          </div>
          <div class="weather__pressure">
            <span>Тиск:</span> {{ weather.pressure }}
          </div>
          <div class="weather__wind">
            <span>Вітер:</span> {{ weather.wind }}
          </div>
        </div>
      </div>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  name: "WeatherComp",
  props: {
    weatherListData: {
      type: Array,
      default: () => [],
    },
    todayTime: {
      type: String,
    },
  },
  data() {
    return {
      weatherList: null,
    };
  },
  computed: {
    filteredWeatherListData() {
      return  this.weatherListData.filter((weather) =>
          weather.city.includes(this.weatherList
        ));
    },
  },
};
</script>

<style lang="css" scoped>
.form {
  margin-bottom: 20px;
}
.weather__top {
  display: flex;
  margin-bottom: 15px;
}
.weather__top__time {
  margin-left: 10px;
}
.weather__in__city {
  display: flex;
  align-items: center;
}
.weather__temp {
  display: flex;
  align-items: center;
}
.temprature {
  font-size: 22px;
}
.weather__param {
  margin-left: 60px;
  font-size: 16px;
}
.weather__param span {
  color: gray;
  font-size: 14px;
}
.term__img {
  max-width: 50px;
}
</style>
