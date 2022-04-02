<template>
  <div class="container">
    <div class="header">
      <ul class="top-header">
        <li class="Logo">
          <img src="../assets/img/Launch-App.png" alt="" />
        </li>
        <li class="projectName">HERESY.DAO</li>
        <li>
          <nuxt-link class="faqsword" to="/">HOME</nuxt-link>
        </li>
        <li>
          <nuxt-link class="faqsword" to="/">TOKEN ECONOMY</nuxt-link>
        </li>
        <li>
          <nuxt-link class="faqsword" to="/faqs">FAQS</nuxt-link>
        </li>
        <li>WHITE PAPER</li>
        <li class="medium">
          <div class="icons">
            <p @click="jumpTelegram()">
              <img src="../assets/img/tg-idle-1.png" alt="" />
            </p>
            <p @click="jumpTwitter()">
              <img src="../assets/img/Twitter-Idle.png" alt="" />
            </p>
          </div>
          <div>Buy HERESY now on Pancakeswap</div>
        </li>
      </ul>
    </div>
    <ul class="mainbox">
      <li v-for="item in FAQLIST" :key="item.ID">
        <div class="FAQ-tip" @click="Faqshow(item)">{{ item.FAQ }}</div>
        <div class="ans" v-if="item.isshow">{{ item.ANS }}</div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      change: true,
      activeid: "1",
      FAQLIST: [
        { ID: "1", FAQ: "aaa", ANS: "1234567", isshow: false },
        { ID: "2", FAQ: "aaa", ANS: "1234567", isshow: false },
        { ID: "3", FAQ: "aaa", ANS: "1234567", isshow: false },
        { ID: "4", FAQ: "aaa", ANS: "1234567", isshow: false },
      ],
    };
  },
  methods: {
    Faqshow(item) {
      this.FAQLIST.forEach((val) => {
        if (val.ID == item.ID) {
          val.isshow = true;
        } else {
          val.isshow = false;
        }
      });
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
  width: 120px;
  height: 60px;
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

.mainbox {
  width: 100%;
  margin: 0;
  padding: 0;
  width: auto;
  height: calc(100vh - 132px);
  list-style: none;
}
.mainbox li {
  width: auto;
  height: auto;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: center;
  color: #fff;
  font-size: 16px;
  border-bottom: 1px solid #fff;
  padding: 0 50px;
}

.FAQ-tip {
  width: 100%;
  height: 20px;
  cursor: pointer;
  padding: 20px;
}

.ans {
  width: 100%;
  height: auto;
  padding: 20px;
}
</style>
