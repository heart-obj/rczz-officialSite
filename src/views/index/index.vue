<template>
  <div class="container">
    <header>
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
    </header>
  </div>
</template>
<script>
import HeaderBox from '@/views/header'
export default {
  name: 'Index',
  components: {
    HeaderBox
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
  width: 100%;
  background: gray;
  position: relative;
}
header {
  width: 100%;
  position: fixed;
  top: 0;
  left: 0;
}
.logo-box {
  display: inline-block;
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
