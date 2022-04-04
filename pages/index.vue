<template>
  <div class="container">
    <div class="header">
      <ul class="top-header">
        <li class="Logo">
          <img src="~/assets/img/logo.png" alt="" />
        </li>
        <li class="projectName">
          <nuxt-link class="faqsword" to="/">HERESY.DAO</nuxt-link>
        </li>
        <li @click="changeOne()">
          <nuxt-link class="faqsword" to="/">HOME</nuxt-link>
        </li>
        <li @click="changeTwo()">TOKEN ECONOMY</li>
        <li>
          <nuxt-link class="faqsword" to="/faqs">FAQS</nuxt-link>
        </li>
        <li>WHITE PAPER</li>
        <li class="medium">
          <div class="icons">
            <p @click="jumpTelegram()">
              <img src="~/assets/img/tg-idle-1.png" alt="" />
            </p>
            <p @click="jumpTwitter()">
              <img src="~/assets/img/Twitter-Idle.png" alt="" />
            </p>
          </div>
          <div>Buy HERESY now on Pancakeswap</div>
        </li>
      </ul>
    </div>
    <!-- ===================== -->
    <div class="content">
      <div class="main bgpicture1" v-show="showPic1"></div>
      <div class="main bgpicture2" v-show="showPic2"></div>
      <ul class="discbox">
        <li
          @click="changeOne()"
          :class="activeid == '1' ? 'changeColor' : ''"
        ></li>
        <li
          @click="changeTwo()"
          :class="activeid == '2' ? 'changeColor' : ''"
        ></li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "index",
  data() {
    return {
      showPic1: true,
      showPic2: false,
      activeid: "1",
    };
  },
  methods: {
    changeOne() {
      this.showPic1 = true;
      this.showPic2 = false;
      this.activeid = "1";
    },
    changeTwo() {
      this.showPic1 = false;
      this.showPic2 = true;
      this.activeid = "2";
    },
    jumpTelegram() {
      window.open("https://t.me/newseacommunitym");
    },
    jumpTwitter() {
      window.open("https://twitter.com/shijianlimilia1");
    },
  },
  mounted() {},
};
</script>

<style scoped>
.container {
  width: 100%;
  height: 100vh;
  background-color: rgba(0, 0, 0, 0.9);
}
.header {
  width: 100%;
  height: auto;
  color: #fff;
  background-color: rgba(0, 0, 0, 0.3);
  display: flex;
  justify-content: flex-start;
  align-items: center;
}

.top-header {
  width: 100%;
  height: 100px;
  display: flex;
  justify-content: space-around;
  align-items: center;
  list-style: none;
}

.Logo {
  width: auto;
  height: auto;
  display: flex;
  justify-content: center;
  align-items: center;
}

.Logo img {
  width: auto;
  height: 90px;
  display: flex;
  justify-content: center;
  align-items: center;
}

.projectName {
  height: 70px;
  font-size: 36px;
  display: flex;
  justify-content: center;
  align-items: center;
  font-family: "Gill Sans", "Gill Sans MT", Calibri, "Trebuchet MS", sans-serif;
}

.faqsword {
  color: #fff;
  text-decoration: none;
}

.top-header li {
  cursor: pointer;
}

.medium {
  width: 280px;
  height: 70px;
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  align-items: flex-start;
}

.icons {
  height: 35px;
  display: flex;
  justify-content: flex-start;
  align-items: center;
}
.icons p {
  width: 25px;
  height: 25px;
  border-radius: 360px;
  display: flex;
  justify-content: center;
  align-items: center;
  cursor: pointer;
  margin-right: 15px;
}

.icons p img {
  width: 25px;
  height: 25px;
}

.content {
  width: 100%;
  height: 100vh;
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
}

.main {
  width: 100%;
  height: 100%;
  overflow-x: hidden;
}

.discbox {
  width: auto;
  height: auto;
  list-style-type: none;
  color: #fff;
  position: absolute;
  left: 0;
  bottom: 50%;
}
.discbox li {
  width: 10px;
  height: 10px;
  border-radius: 360px;
  display: flex;
  justify-content: center;
  align-items: center;
  border: 1px solid rgba(299, 299, 299, 0.9);
  margin-bottom: 15px;
  cursor: pointer;
}
.changeColor {
  width: 10px;
  height: 10px;
  border-radius: 360px;
  display: flex;
  justify-content: center;
  align-items: center;
  border: 1px solid rgba(299, 299, 299, 0.5);
  background-color: #901717;
}

.bgpicture1 {
  background-image: url("../assets/img/bg4.png");
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
}
.bgpicture2 {
  background-image: url("../assets/img/bg1.png");
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
}
</style>
