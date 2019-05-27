<template>
  <div>
    <div class="box1">
      <div class="text-title1">Corporate business</div>
      <div class="text-title2">
        <span class="line line1"></span>
        <span class="text">公司业务</span>
        <span class="line line2"></span>
      </div>
      <div class="text-title3">为您提供更多优质服务</div>
      <div class="text-title4">
        9年软件高端定制服务商，为客户研发的产品有10多款拿到投融资，合作的伙伴遍布全球20多个国家。始终坚持“要么不做，要么做好”的理念。在互联网领域已经小有名气！
      </div>
      <div class="business-box" :style="{background: 'url('+ business_bg +')no-repeat center', 'background-size': '100% 100%'}">
        <div class="middle-icon"></div>
        <div class="middle-icon1"></div>
        <div class="middle-icon2"></div>
        <span class="col-box" v-for="(item, i) in businesslist" :key="i" :class="'col-box'+i">
          <div class="col-h">{{item.title}}</div>
          <span class="col-text">{{item.text}}</span>
        </span>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'Business',
  data () {
    return {
      business_bg: './static/img/business_bg.png',
      businesslist: [
        {
          title: 'APP高端定制',
          text: '多年项目开发，我们拥有 合理且高效的项目管理机制 以及经验丰富的研发团队',
          hover: false
        },
        {
          title: '网站定制与模板开发',
          text: '我们拥有近50套网站模板以及 300多个网站定制案例，能够快速、 低成本的为您搭建自己的网站。 也可以为您定制服务！',
          hover: false
        },
        {
          title: '系统开发',
          text: 'OA管理系统、CRM管理系统、 ERP管理系统以及其他类似管理系统， 我们开发案例很多。移动办公、 电脑桌面应用，经验丰富',
          hover: false
        },
        {
          title: '微信应用快速定制',
          text: '我们提供一站式微信应用快速定制服务。 包括微信公众号申请、小程序账号申请、 资质认证、域名备案、接口申请等。',
          hover: false
        },
        {
          title: '棋牌游戏定制服务',
          text: '4年棋牌手机游戏开发经验， 300多款棋牌游戏，涵盖了大多数 常见棋牌游戏。支持源码售卖',
          hover: false
        },
        {
          title: '一站式服务代办',
          text: '商标注册、软著申请、 开发者账号申请、接口申请... 我们为您一站式服务全部搞定。 让您省力省心安心更放心！',
          hover: false
        },
        {
          title: '人员外派与专属服务',
          text: '我们只聘用至少3年相关 领域经验的人才，保证人才质量， 不仅可以提供人员驻场，还可以为您 提供指定人才全天全身心只为您服务！',
          hover: false
        },
        {
          title: '技术支持',
          text: '运用我们丰富的经验，可以为您的 产品提供可行的项目建设方案和 项目开发技术顾问，让您的产品符合 互联网思维、真正为您保驾护航！',
          hover: false
        },
        {
          title: '视觉设计',
          text: 'LOGO设计、UE/UI设计、 包装设计、企业策划、海报制作， 我们提供一对一定制服务， 直到设计出您满意的作品为止。',
          hover: false
        },
        {
          title: '服务器应用开发',
          text: '我们拥有强大的技术团队、 专业的产品团队和专心的售后 服务团队，为您提供最专业的 互联网IT咨询及软件开发。',
          hover: false
        }
      ]
    }
  }
}
</script>
<style scoped>
.box1 {
  width: 100%;
  padding-bottom: 8vw;
}
.box1 .text-title1 {
  font-size: 1.5vw;
  font-weight: bold;
  color: #dddddd;
}
.box1 .text-title2 {
  font-size: 1.9vw;
  color: #499aff;
  font-weight: bold;
  position: relative;
  display: flex;
  justify-content: center;
}
.box1 .text-title2 .text{
  font-size: 1.9vw;
  color: #499aff;
  font-weight: bold;
  vertical-align: middle;
  padding: 0 10px;
}
.box1 .text-title2 .line {
  display: inline-block;
  width: calc(50% - 100px);
  height: 1px;
  border: 1px solid #dcdcdc;
}
.box1 .text-title2 .line1 {
  position: absolute;
  top: 50%;
  left: 0;
  margin-top: -0.5px;
}
.box1 .text-title2 .line2 {
  position: absolute;
  top: 50%;
  right: 0;
  margin-top: -0.5px;
}
.box1 .text-title3 {
  color: #333333;
  font-size: 0.73vw;
}
.box1 .text-title4 {
  display: inline-block;
  box-sizing: border-box;
  padding: 1.56vw 15.6vw 0 15.6vw;
  color: #999999;
  font-size: 0.8vw;
}

.business-box {
  width: 100%;
  height: 50vw;
  margin: 10px 0 0 0;
  position: relative;
}
.middle-icon {
  width: 17.5vw;
  height: 17.5vw;
  background: url('./img/centercircle.png') no-repeat center;
  background-size: 100% 100%;
  position: absolute;
  left: 0;
  top: 0;
  right: 0;
  bottom: 0;
  margin: auto;
}
.middle-icon1 {
  width: 30vw;
  height: 22vw;
  border: 1px dashed #499aff;
  border-radius: 50% / 50%;
  position: absolute;
  left: 0;
  top: 0;
  right: 0;
  bottom: 0;
  margin: auto;
}
.middle-icon2 {
  width: 50vw;
  height: 40vw;
  border: 1px dashed #499aff;
  border-radius: 50% / 50%;
  position: absolute;
  left: 0;
  top: 0;
  right: 0;
  bottom: 0;
  margin: auto;
}
.business-box .col-box {
  display: inline-block;
  /* width: 12.76vw;
  max-height: 9.3vw; */
  background: #ffffff;
  border: 1px solid #499aff;
  border-radius: 3px;
  cursor: pointer;
}
.business-box .col-box:hover {
  background: #499aff;
  box-shadow: 0 0 15px rgba(73, 154, 255, 0.8)
}
.business-box .col-box:hover .col-h{
  color: #ffffff;
}
.business-box .col-box:hover .col-text{
  color: #ffffff;
}
.col-box .col-h {
  font-size: 1.2vw;
  font-weight: bold;
  color: #000;
  position: relative;
  padding: 0 10px;
  padding-bottom: 8px;
}
.col-box .col-h::after {
  content: '';
  display: inline-block;
  width: 42px;
  height: 4px;
  background: #0c7efc;
  position: absolute;
  bottom: 1px;
  left: 0;
  right: 0;
  margin: 0 auto;
}
.col-box .col-text {
  display: inline-block;
  max-width: 12.76vw;
  font-size: 12px;
  color: #666666;
  padding: 8px 10px;
}
.col-box0 {
  position: absolute;
  left: 18vw;
  top: 17vw;
}
.col-box1 {
  position: absolute;
  left: 27vw;
  top: 7vw;
}
.col-box2 {
  position: absolute;
  left: 44vw;
  top: 2vw;
}
.col-box3 {
  position: absolute;
  right: 25vw;
  top: 5vw;
}
.col-box4 {
  position: absolute;
  right: 18vw;
  top: 16vw;
}
.col-box5 {
  position: absolute;
  right: 17vw;
  bottom: 17vw;
}
.col-box6 {
  position: absolute;
  right: 25vw;
  bottom: 8vw;
}
.col-box7 {
  position: absolute;
  left: 40vw;
  bottom: 2vw;
}
.col-box8 {
  position: absolute;
  left: 23vw;
  bottom: 7vw;
}
.col-box9 {
  position: absolute;
  left: 17vw;
  bottom: 17vw;
}
</style>
