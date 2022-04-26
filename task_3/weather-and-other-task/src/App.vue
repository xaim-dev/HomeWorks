<template>
  <div class="container">
    <persimmon-comp
      logo="https://icons.veryicon.com/png/o/food--drinks/fruit-icon-1/persimmon-3.png"
      logo-text="persimmon"
      header-text="Рекламна мережа"
      content-image="https://yaskravaklumba.com.ua/image/cache/catalog/derevya/hurma/2_bycheserdce_2-500x500.jpg"
      content-title="Соковита хурма"
    />
    <weather-comp
      :weather-list-data="listData"
      today-time="сьогодні о 9:00"
    />
    <table-comp
      :table-list-data="productList"
    />
  </div>
</template>

<script>
import PersimmonComp from "./components/PersimmonComp";
import WeatherComp from "./components/WeatherComp";
import TableComp from "./components/TableComp";

export default {
  name: "App",

  components: {
    PersimmonComp,
    WeatherComp,
    TableComp,
  },

  data() {
    return {
      listData: [
        {
          id: 1,
          city: "Ужгород",
          termImg: "https://www.svgrepo.com/show/284594/thermometer-temperature.svg",
          temp: "12°",
          humid: "97%",
          pressure: "748 мм",
          wind: "0 м/с",
        },
        {
          id: 2,
          city: "Львів",
          termImg: "https://www.svgrepo.com/show/284594/thermometer-temperature.svg",
          temp: "13°",
          humid: "95%",
          pressure: "743 мм",
          wind: "2 м/с",
        },
        {
          id: 3,
          city: "Київ",
          termImg: "https://www.svgrepo.com/show/284594/thermometer-temperature.svg",
          temp: "14°",
          humid: "90%",
          pressure: "738 мм",
          wind: "4 м/с",
        },
      ],
      productList: [
        {
          id: '1',
          name: 'сир',
          price: 100,
          pdv: 5,
        },
        {
          id: '2',
          name: 'молоко',
          price: 50,
          pdv: 5,
        },
        {
          id: '3',
          name: 'вино',
          price: 150,
          pdv: 5,
        },
      ],
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.container {
  display: flex;
  justify-content: space-evenly;
}
</style>
