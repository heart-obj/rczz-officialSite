<template>
  <div class="container">
    <header>
      <div class="nav-bar-box">
        <div class="logo-box">
          <div class="logo">极越科技</div>
        </div>
        <div class="tab-box" :class="showTab ? 'showTab' : ''">
          <HeaderBox></HeaderBox>
        </div>
        <div class="navbar-toggle" @click="showTabFunc">
          <span class="glyphicon glyphicon-list"></span>
          <span class="glyphicon glyphicon-list"></span>
          <span class="glyphicon glyphicon-list"></span>
        </div>
      </div>
    </header>
    <div class="plan-box">
      <div class="plan-bg"></div>
    </div>
    <div class="content-box">
      <Honor></Honor>
      <Business></Business>
    </div>
    <footer></footer>
  </div>
</template>
<script>
import HeaderBox from '@/views/header'
import Honor from '@/components/honorlist'
import Business from '@/components/business'
export default {
  name: 'Index',
  components: {
    HeaderBox,
    Honor,
    Business
  },
  data () {
    return {
      navbtn: false,
      showTab: false
    }
  },
  methods: {
    showTabFunc () {
      this.showTab = !this.showTab
    }
  }
}
</script>
<style scoped>
.container {
  width: 100% !important;
  max-width: 100% !important;
  padding: 0 !important;
  background: #ffffff;
  position: relative;
}
header {
  height: 48vw;
  background: url('img/banner1.png') no-repeat center;
  background-size: 100% 100%;
}
.nav-bar-box {
  display: inline-block;
  width: 100%;
  position: fixed;
  top: 0;
  left: 0;
  background: rgba(255, 255, 255, 0.6);
  z-index: 99;
}
.logo-box {
  display: none;
}
.logo {
  height: 73px;
  position: relative;
  line-height: 73px;
  font-size: 30px;
  padding-top: 10px;
  float: left;
}
.logo::after {
  display: inline-block;
  content: '';
  width: 65px;
  height: 73px;
  background: url('img/logo.png') no-repeat center;
  position: absolute;
  left: -70px;
  bottom: 0px;
}
.contact-box {
  display: inline-block;
}
.showTab {
  display: block !important;
}
.navbar-toggle {
  width: 32px;
  position: absolute;
  right: 10px;
  top: 20px;
  border: 1px solid #333;
  border-radius: 4px;
  background-color: #333;
  cursor: pointer;
}
.navbar-toggle span {
  display: block;
  margin: 5px;
  width: 22px;
  height: 2px;
  border-radius: 1px;
  background: #ffffff;
}
.plan-box {
  box-sizing: border-box;
  width: 100;
  height: 25.6vw;
  background: #ffffff;
  position: relative;
  z-index: 11;

}
.plan-box .plan-bg {
  width: 78vw;
  height: 23.6vw;
  position: absolute;
  top: -3.6vw;
  left: 0;
  right: 0;
  margin: 0 auto;
  background: url('img/index.png')no-repeat center;
  background-size: 100% 100%;
}
@media (min-width: 1366px) {
  .logo-box {
    display: inline-block;
  }
}
@media (min-width: 768px) {
  .tab-box {
    display: inline-block;
  }
  .logo {
    margin-right: 180px;
  }
  .navbar-toggle {
    display: none;
  }
}
@media (max-width: 768px) {
  .tab-box {
    display: none;
  }
  .navbar-toggle {
    display: inline-block;
  }
}

</style>
