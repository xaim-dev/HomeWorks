<template>
  <div>
    <div class="wrapper">
      <div class="header">
        <div class="logo__inner">
          <img class="logo__img" :src="logo" />
          <div class="logo__text">{{ logoText }}</div>
        </div>
        <div class="header__text">{{ headerText }}</div>
      </div>
      <div class="content">
        <img class="content__img" :src="contentImage" />
        <div class="content__title">{{ contentTitle }}</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "PersimmonComp",

  props: {
    logo: {
      type: String,
      default: "http://giuseppe.com.ua/img/no-photo.png",
    },
    logoText: {
      type: String,
    },
    headerText: {
      type: String,
    },
    contentImage: {
      type: String,
      default: "http://giuseppe.com.ua/img/no-photo.png",
    },
    contentTitle: {
      type: String,
      default: "no title",
    },
  },
};
</script>

<style lang="css" scoped>
.wrapper {
  max-width: 400px;
  margin-bottom: 30px;
}
.header {
  background-color: #181515;
  display: flex;
  justify-content: space-between;
  align-items: center;
  border-top-left-radius: 10px;
  border-top-right-radius: 10px;
}
.logo__inner {
  display: flex;
  align-items: center;
  padding: 10px;
}
.logo__img {
  max-width: 30px;
}
.logo__text {
  color: #ff8016;
  font-family: "Rubik Moonrocks", cursive;
  font-weight: 400;
  font-size: 16px;
  padding-left: 5px;
}
.header__text {
  color: #fff;
  font-family: "Grape Nuts", cursive;
  font-weight: 400;
  font-size: 18px;
  padding-right: 10px;
}
.content {
  background-color: #d5cccc;
  border-bottom-right-radius: 10px;
  border-bottom-left-radius: 10px;
}
.content__img {
  max-width: 250px;
  padding: 10px 0;
  border-radius: 60px;
}
.content__title {
  color: #ff8016;
  font-family: "Grape Nuts", cursive;
  font-weight: 400;
  font-size: 22px;
  padding-bottom: 10px;
  padding-left: 10px;
  text-align: left;
}
</style>