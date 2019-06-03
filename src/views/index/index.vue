<template>
  <div class="app-container" @scroll="scroll">
    <div>
      <header ref="uptop">
        <div class="nav-bar-box" :class="offsetTop ? 'offsetTop' : ''">
          <div class="logo-box">
            <div class="logo">极越科技</div>
          </div>
          <div class="tab-box" :class="showTab ? 'showTab' : ''">
            <HeaderBox @tabClick="tabClick" :activeNav="activeNav"></HeaderBox>
          </div>
          <!-- <div class="navbar-toggle" @click="showTabFunc">
            <span class="glyphicon glyphicon-list"></span>
            <span class="glyphicon glyphicon-list"></span>
            <span class="glyphicon glyphicon-list"></span>
          </div> -->
        </div>
      </header>
      <div class="plan-box">
        <div class="plan-bg"></div>
      </div>
      <div class="content-box">
        <Honor ref="Honor"></Honor>
        <Business ref="Business"></Business>
        <Reason ref="Reason"></Reason>
        <GoodCase ref="GoodCase"></GoodCase>
        <Aboutus ref="Aboutus"></Aboutus>
        <CooperativePartner ref="CooperativePartner"></CooperativePartner>
      </div>
      <footer>
        <div class="row footerRow1">
          <div class="col-3 col1">快速联系</div>
          <div class="col-3 col2">
            <span class="qq" @click="showTip('qqtip')" data-toggle="modal" data-target="#exampleModal"></span>
            <div class="tip-box qqtip-box" v-show="qqtip && !ifMobile">
              <span class="close" @click="showTip('qqtip')">关闭</span>
              <span class="tip-text">1808569213</span>
            </div>
          </div>
          <div class="col-3 col2">
            <span class="wx" @click="showTip('wxtip')"></span>
            <div class="tip-box wxtip-box" v-show="wxtip && !ifMobile">
              <span class="close" @click="showTip('wxtip')">关闭</span>
              <span class="tip-text"></span>
            </div>
          </div>
          <div class="col-3 col2">
            <div class="tip-box phonetip-box" v-show="phonetip && !ifMobile">
              <span class="close" @click="showTip('phonetip')">关闭</span>
              <span class="tip-text">18428088011</span>
            </div>
            <span class="cell" @click="showTip('phonetip')"></span>
          </div>
        </div>
      </footer>
      <FooterPage></FooterPage>
    </div>
    <div class="mobile-footer-tab row">
      <div class="col-2" v-for="(item, i) in navlis" :key="i">
        <div :class="item.prop === activeNav ? 'activeNav' : ''" @click="tabClick(item.prop)">{{ item.label }}</div>
      </div>
    </div>
    <div class="right-tip" v-show="showRight">
      <div class="right-col wxRight-col">
        <div class="wxRight-icon"></div>
      </div>
      <div class="right-col phoneRight-col">
        <div class="phoneRight-icon">18428088011</div>
      </div>
      <div class="right-col returnRight-col" @click="tabClick('uptop')">返回顶部</div>
    </div>
    <!-- 移动端快速联系弹窗 -->
    <div class="model-tip" v-show="showModelTip && ifMobile">
      <div class="model-container">
        <div class="model-h">
          <span class="close-model" @click="closeModel">关闭</span>
        </div>
        <div class="model-content">
          <span class="tipContent-box qq-icon" v-show="qqtip">1808569213</span>
          <span class="tipContent-box wx-icon" v-show="wxtip"></span>
          <span class="tipContent-box phone-icon" v-show="phonetip">1808569213</span>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import HeaderBox from '@/views/header'
import Honor from '@/components/honorlist'
import Business from '@/components/business'
import Reason from '@/components/reason'
import GoodCase from '@/components/goodCase'
import Aboutus from '@/components/aboutus'
import CooperativePartner from '@/components/cooperativePartner'
import FooterPage from '@/components/footerPage'
export default {
  name: 'Index',
  components: {
    HeaderBox,
    Honor,
    Business,
    Reason,
    GoodCase,
    Aboutus,
    CooperativePartner,
    FooterPage
  },
  data () {
    return {
      navbtn: false,
      showTab: false,
      offsetTop: false,
      qqtip: false,
      wxtip: false,
      phonetip: false,
      ifMobile: false,
      showModelTip: false,
      screenWidth: '',
      screenHeight: '',
      navlis: [
        {
          prop: 'uptop',
          label: '首页'
        },
        {
          prop: 'Honor',
          label: '荣誉资质'
        },
        {
          prop: 'Business',
          label: '公司业务'
        },
        {
          prop: 'GoodCase',
          label: '精彩案例'
        },
        {
          prop: 'Aboutus',
          label: '关于我们'
        },
        {
          prop: 'CooperativePartner',
          label: '合作伙伴'
        }
      ],
      showRight: false,
      scrollTop: 0,
      activeNav: 'uptop'
    }
  },
  watch: {
    screenWidth: {
      handler (newVal) {
        this.screenWidth = newVal
        if (newVal < 1200) {
          this.ifMobile = true
        } else {
          this.ifMobile = false
        }
      }
    },
    screenHeight: {
      handler (newVal) {
        this.screenHeight = newVal
      }
    }
  },
  mounted () {
    this.screenWidth = document.body.clientWidth
    this.screenHeight = document.body.clientHeight
    window.onresize = () => {
      return (() => {
        this.screenWidth = document.body.clientWidth
        this.screenHeight = document.body.clientHeight
      })()
    }
    document.querySelector('.app-container').addEventListener('scroll', this.windowScroll)
  },
  methods: {
    showTabFunc () {
      this.showTab = !this.showTab
    },
    tabClick (ref) {
      if (ref === 'uptop') {
        document.querySelector('.app-container').scrollTop = 0
      } else {
        let eloffsetTop = this.$refs[ref].$el.offsetTop
        document.querySelector('.app-container').scrollTop = eloffsetTop
      }
    },
    showTip (type) {
      this[type] = !this[type]
      this.showModelTip = this[type]
    },
    closeModel () {
      this.showModelTip = false
      this.qqtip = false
      this.wxtip = false
      this.phonetip = false
    },
    scroll (event) {
      const eventScroll = event.target.scrollTop
      if (eventScroll > 0) {
        this.offsetTop = true
      } else {
        this.offsetTop = false
      }
    },
    windowScroll () {
      this.scrollTop = document.querySelector('.app-container').scrollTop
      this.navlis.map(item => {
        if (item.prop !== 'uptop') {
          if (this.scrollTop >= (this.$refs[item.prop].$el.offsetTop - 100)) {
            this.showRight = true
            this.activeNav = item.prop
          }
        } else if (item.prop === 'uptop') {
          this.showRight = false
          this.activeNav = 'uptop'
        }
      })
    }
  }
}
</script>
<style scoped>
@keyframes fade-in {
  0% {opacity: 0;}/*初始状态 透明度为0*/
  20% {opacity: 0.2;}/*过渡状态 透明度为0*/
  40% {opacity: 0.4;}/*过渡状态 透明度为0*/
  60% {opacity: 0.6;}/*过渡状态 透明度为0*/
  80% {opacity: 0.8;}/*过渡状态 透明度为0*/
  100% {opacity: 1;}/*结束状态 透明度为1*/
}
@-webkit-keyframes fade-in {/*针对webkit内核*/
  0% {opacity: 0;}/*初始状态 透明度为0*/
  20% {opacity: 0.2;}/*过渡状态 透明度为0*/
  40% {opacity: 0.4;}/*过渡状态 透明度为0*/
  60% {opacity: 0.6;}/*过渡状态 透明度为0*/
  80% {opacity: 0.8;}/*过渡状态 透明度为0*/
  100% {opacity: 1;}/*结束状态 透明度为1*/
}
.app-container {
  width: 100% !important;
  height: 100%;
  overflow-y: auto;
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
  z-index: 99;
}
.offsetTop {
  background: rgba(22, 21, 21, 0.6);
  box-shadow: 0 0 10px rgba(22, 21, 21, 0.6);
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
footer {
  position: sticky;
  bottom: 0;
  z-index: 111;
  box-shadow: -5px 0 10px rgba(0, 0, 0, .5);
}
footer .footerRow1 {
  width: 100%;
  height: 100px;
  margin: 0;
  background: #499aff;
}
.footerRow1 .col1 {
  font-size: 2vw;
  line-height: 100px;
  font-weight: bold;
}
.footerRow1 .col2 {
  font-size: 1.25vw;
  position: relative;
}
.footerRow1 .col2>span {
  position: relative;
  cursor: pointer;
  display: inline-block;
  width: 11.77vw;
  height: 3.125vw;
  position: absolute;
  border-radius: 9px;
  left: 0;
  right: 0;
  top: 0;
  bottom: 0;
  margin: auto;
  box-shadow: 0 0 10px rgba(0, 0, 0, .5);
}
.footerRow1 .col2 .qq {
  background: url('./img/btn_qq.png') no-repeat center;
  background-size: 100% 100%;
}
.footerRow1 .col2 .wx {
  background: url('./img/btn_Wechat.png') no-repeat center;
  background-size: 100% 100%;
}
.footerRow1 .col2 .cell {
  background: url('./img/btn_phone.png') no-repeat center;
  background-size: 100% 100%;
}
.footerRow1 .col2 .tip-box {
  width: 19.7vw;
  height: 14.8vw;
  position: absolute;
  left: 50%;
  right: 0;
  bottom: 100px;
  margin-left: -9.85vw;
  background: #ffffff;
  box-shadow: 0 0 10px rgba(0, 0, 0, .5);
  text-align: center;
  border-radius: 5px;
}
.footerRow1 .col2 .tip-box {
  animation: fade-in;/*动画名称*/
  animation-duration: 400ms;/*动画持续时间*/
  -webkit-animation:fade-in 400ms;/*针对webkit内核*/
}
.footerRow1 .tip-box::after {
  content: '';
  display: inline-block;
  width: 0;
  height: 0;
  border-width: 15px 15px 0;
  border-style: solid;
  border-color:#ffffff transparent transparent;
  position: absolute;
  bottom: -15px;
  left: 0;
  right: 0;
  margin: auto;
  z-index: 11
}
.tip-box .close {
  position: absolute;
  top: 8px;
  right: 10px;
  color: #499aff;
  font-size: 14px;
  cursor: pointer;
  transition: 2s
}
.tip-box .tip-text {
  width: 130px;
  height: 30px;
  font-size: 16px;
  color: #499aff;
  position: absolute;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  margin: auto;
  line-height: 30px;
}
.tip-box .tip-text::after {
  content: '';
  display: inline-block;
  width: 30px;
  height: 30px;
  position: absolute;
  top: 0;
  bottom: 0;
  left: -30px;
  margin: auto;
}
.qqtip-box .tip-text::after {
  background: url('./img/icon_qq.png')no-repeat center;
  background-size: 100% 100%;
}
.wxtip-box .tip-text {
  width: 70%;
  height: 70%;
  background: url('./img/icon_Wechat.png')no-repeat center;
  background-size: 100% 100%;
}
.phonetip-box .tip-text::after {
  background: url('./img/icon_phone.png')no-repeat center;
  background-size: 100% 100%;
}
.model-tip{
  animation: fade-in;/*动画名称*/
  animation-duration: 400ms;/*动画持续时间*/
  -webkit-animation:fade-in 400ms;/*针对webkit内核*/
}
.model-tip {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, .5);
  z-index: 999;
}
.model-tip .model-container {
  width: 280px;
  background: #ffffff;
  border-radius: 5px;
  position: absolute;
  top: 80px;
  left: 0;
  right: 0;
  margin: auto;
}
.model-h {
  position: relative;
  height: 30px;
  line-height: 30px;
  color: #499aff;
  font-size: 16px;
}
.close-model {
  font-size: 14px;
  position: absolute;
  right: 0;
  top: 0px;
  margin-right: 8px;
  color: #499aff;
  cursor: pointer;
}
.model-content {
  padding: 10px;
  color: #499aff;
}
.tipContent-box {
  position: relative;
  display: inline-block;
  padding: 60px 10px;
}
.qq-icon::after {
  content: '';
  display: inline-block;
  width: 30px;
  height: 30px;
  position: absolute;
  top: 0;
  bottom: 0;
  left: -30px;
  margin: auto;
  background: url('./img/icon_qq.png')no-repeat center;
  background-size: 100% 100%;
}
.phone-icon::after {
  content: '';
  display: inline-block;
  width: 30px;
  height: 30px;
  position: absolute;
  top: 0;
  bottom: 0;
  left: -30px;
  margin: auto;
  background: url('./img/icon_phone.png')no-repeat center;
  background-size: 100% 100%;
}
.wx-icon {
  width: 250px;
  height: 250px;
  padding: 0;
  background: url('./img/icon_Wechat.png')no-repeat center;
  background-size: 100% 100%;
}
/* 移动端样式 */
.mobile-footer-tab {
  width: 100%;
  height: 50px;
  position: fixed;
  bottom: 0;
  left: 0;
  background: rgba(0, 0, 0, .7);
  z-index: 111;
  display: none;
  justify-content:space-between;
  flex-wrap: nowrap;
  margin: 0;
}
.mobile-footer-tab div {
  display: inline-block;
  font-size: 0.16vw;
  padding: 0;
  line-height: 50px;
}
.mobile-footer-tab>div {
  position: relative;
}
.mobile-footer-tab .activeNav {
  width: 100%;
  height: 55px;
  line-height: 60px;
  background: #109ffd;
  position: absolute;
  bottom: 0;
  left: 0;
}
.right-tip {
  width: 50px;
  background: #ffffff;
  position: fixed;
  right: 10px;
  bottom: 30%;
  z-index: 999;
  display: flex;
  flex-direction:column;
}
.right-tip .right-col {
  width: 100%;
  height: 55px;
  cursor: pointer;
  position: relative;
}
.wxRight-col {
  background: #499aff url('./img/wechat.png') no-repeat center;
  background-size: 50% 40%;
}
.wxRight-col:hover .wxRight-icon {
  display: block;
}
.wxRight-col .wxRight-icon {
  display: none;
  width: 100px;
  height: 100px;
  background: url('./img/icon_Wechat.png') no-repeat center;
  background-size: 100% 100%;
  box-shadow: 0 0 15px rgba(0, 0, 0, .5);
  position: absolute;
  left: -110px;
  top: 50%;
  margin-top: -50px;
}
.wxRight-col .wxRight-icon::after {
  display: block;
  content: '';
  width: 10px;
  height: 10px;
  border-width: 10px 0 10px 10px;
  border-style: solid;
  border-color: transparent transparent transparent #ffffff;
  position: absolute;
  top: 50%;
  right: -10px;
  margin-top: -5px;
  z-index: 11;
}
.phoneRight-col {
  background: #499aff url('./img/phone.png') no-repeat center;
  background-size: 50% 48%;
  margin: 1px 0;
}
.phoneRight-col:hover .phoneRight-icon {
  display: block;
}
.phoneRight-col .phoneRight-icon {
  display: none;
  height: 50px;
  font-size: 16px;
  font-weight: bold;
  line-height: 50px;
  color: #499aff;
  background: #ffffff;
  box-shadow: 0 0 15px rgba(0, 0, 0, .5);
  padding: 0 20px;
  position: absolute;
  right: 60px;
  top: 0;
  bottom: 0;
  margin: auto;
}
.phoneRight-col .phoneRight-icon::after {
  display: block;
  content: '';
  width: 10px;
  height: 10px;
  border-width: 10px 0 10px 10px;
  border-style: solid;
  border-color: transparent transparent transparent #ffffff;
  position: absolute;
  top: 50%;
  right: -10px;
  margin-top: -10px;
  z-index: 11;
}
.returnRight-col {
  background: #499aff url('./img/return.png') no-repeat center;
  background-size: 50% 25%;
  background-position-y: 10px;
  line-height: 80px;
  font-size: 12px;
}
@media (min-width: 1366px) {
  .logo-box {
    display: inline-block;
  }
}
@media screen and (max-width: 1200px) {
  footer .footerRow1 {
    height: 70px;
    margin: 0;
  }
  .footerRow1 .col1 {
    line-height: 70px;
    height: 70px;
  }
  .footerRow1 .col2>span {
    width: 70px;
    height: 24px;
    border-radius: 5px;
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
@media screen and (max-width: 768px) {
  .tab-box {
    display: none;
  }
  .mobile-footer-tab {
    display: flex;
  }
  .navbar-toggle {
    display: inline-block;
  }
  footer {
    bottom: 60px;
  }

}

</style>
