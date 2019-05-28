<template>
  <div>
    <div class="box1">
      <div class="text-title1">Perfect case</div>
      <div class="text-title2">
        <span class="line line1"></span>
        <span class="text">精彩案例</span>
        <span class="line line2"></span>
      </div>
      <div class="text-title3">为您提供更多优质服务</div>
      <div class="text-title4">
        9年软件高端定制服务商，为客户研发的产品有10多款拿到投融资，合作的伙伴遍布全球20多个国家。我们一路高歌向前并获得了众多客户的认可，帮助他们快速迈向互联网+时代！
      </div>
      <div class="case-box">
        <div v-for="(item, index) in caselist" :key="index">
          <div :class="index % 2 === 0 ? 'case-col' : 'case-col2'" :style="{background: 'url('+ item.bgimg +')no-repeat'}">
            <div class="case-content">
              <div class="case-title">{{item.title}}</div>
              <span class="case-text" v-html="item.label"></span>
              <div class="case-btn" :style="{background: item.btnBgColor}">查看更多</div>
            </div>
          </div>
        </div>
      </div>
      <div class="mobilecase-box">
        <div v-for="(item, index) in caselist" :key="index" style="margin-top: 100px;">
          <div :class="index % 2 === 0 ? 'mobilecase-col' : 'mobilecase-col2'" :style="{background: 'url('+ item.bgimg +')no-repeat'}">
            <div class="mobilecase-content">
              <div class="mobilecase-title">{{item.title}}</div>
              <span class="mobilecase-text" v-html="item.label" :style="{'text-align': index % 2 === 0 ? 'left' : 'right'}"></span>
              <div class="mobilecase-btn" :style="{background: item.btnBgColor,float: index % 2 === 0 ? 'left' : 'right' }">查看更多</div>
            </div>
            <div class="mobilecase-icon" :style="{background: 'url('+ item.bgimg +')no-repeat'}"></div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'GoodCase', // 精彩案例
  data () {
    return {
      caselist: [
        {
          title: 'APP-西藏布达拉宫智慧导游系统',
          label: '是一款导游平台移动端应用，您可以使用APP<br/>对各个景点进行导航和深入了解，还能申请制作导游包方便规划其他用户的旅行路线<br/>平台上还可以和各地驴友聊天发帖，建立一个小的社交驴友圈同时平台还会推荐景点好吃、好玩、好购物的地方让驴友们了解当地的民俗风情。',
          bgimg: './static/img/caseBg1.png',
          btnBgColor: '#36d49e'
        },
        {
          title: 'Web系统-南昌交警总局交通系统',
          label: '交通系统应用在交通行业，主要使用群体是交警，满足交警的交通信号控制、交通违章处置、稽查布控、智能研判等业务需求，是交通管理部门重要的义务应用平台。<br/>界面设计充分考虑了交互设计、界面设计以及用户体验，<br/>平台具备友好性和易用性，采用科技风格+公安交通元素。',
          bgimg: './static/img/caseBg2.png',
          btnBgColor: '#2e4ca5'
        },
        {
          title: 'APP-新华网新闻客户端',
          label: '新华网新闻客户端是以手机为传播平台，为用户提供新闻资讯<br/>段务的媒介应用程序。具有操作简单、更新快速、<br/>内容丰富、设计人性化、注重交互性的特点，<br/>为用户获取新闻资讯提供了便捷条件。',
          bgimg: './static/img/caseBg3.png',
          btnBgColor: '#1489df'
        },
        {
          title: '后台系统-美国便利店超市系统',
          label: '收银是便利店、超市在系统操作时，最频繁的工作，可谓十分重要。<br/>常用功能提供快捷键、无码/称重商品提供快速选择栏、<br/>收银时可直接修改商品价格等等，都是千帆掌柜为便利店、<br/>超市收银提供的悉心支持。<br/><br/><div style="text-align:right">Lorem Ipsum</div>',
          bgimg: './static/img/caseBg4.png',
          btnBgColor: '#72d367'
        },
        {
          title: 'APP-农信贷银行理财系统',
          label: '农业产业很容易受到自然灾害、气候变化等因素影响，加上信用体系建设不足，<br/>农业金融已经成为国内金融体系最为薄弱的一个环<br/>节。农业信贷APP开发充当农业产业链整合角色，<br/>通过信托产品把农民和社会投资者连接起来，解决种植户扩大土地经营的融资需求<br/>',
          bgimg: './static/img/caseBg5.png',
          btnBgColor: '#1489df'
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
.case-box {
  width: 100%;
}
.case-box .case-col {
  width: 100%;
  height: 31.9vw;
  background-position: right !important;
  background-size: 62% !important;
  position: relative;
}
.case-col .case-content {
  position: absolute;
  left: 10.4vw;
  top: 2vw;
  width: 27.1vw;
}
.case-box .case-col2 {
  width: 100%;
  height: 31.9vw;
  background-position: left !important;
  background-size: 62% !important;
  position: relative;
}
.case-col2 .case-content {
  position: absolute;
  right: 10.4vw;
  top: 2vw;
  width: 27.1vw;
}
.case-content .case-title {
  font-size: 1.875vw;
  color: #36d49e;
  font-weight: bold;
}
.case-content .case-text {
  width: 100%;
  display: inline-block;
  color: #0e0509;
  padding-top: 20px;
  text-align: left;
  font-weight: 700;
}
.case-content .case-btn {
  margin-top: 1vw;
  padding: 14px 36px;
  background: #36d49e;
  color: #ffffff;
  border-radius: 5px;
  float: left;
}
@media (min-width: 768px) {
  .case-box {
    width: 100%;
    display: inline-block;
  }
  .mobilecase-box {
    width: 100%;
    display: none;
  }
}
@media (max-width: 768px) {
  .case-box {
    width: 100%;
    display: none;
  }
  .mobilecase-box {
    width: 100%;
    display: inline-block;
  }
  .mobilecase-box .mobilecase-col {
    width: 100%;
    background-position: right bottom!important;
    background-size: 100% 53% !important;
    padding-bottom: 30.1vw;
  }
  .mobilecase-col .mobilecase-content {
    width: 100%;
  }
  .mobilecase-box .mobilecase-col2 {
    width: 100%;
    background-position: left bottom!important;
    background-size: 100% 53% !important;
    padding-bottom: 30.1vw;
  }
  .mobilecase-col2 .mobilecase-content {
    width: 100%;
  }
  .mobilecase-content .mobilecase-title {
    font-size: 1.875vw;
    color: #36d49e;
    font-weight: bold;
  }
  .mobilecase-content .mobilecase-text {
    width: 100%;
    display: inline-block;
    color: #0e0509;
    padding: 20px;
    font-size: 12px;
    font-weight: 700;
  }
  .mobilecase-content .mobilecase-btn {
    font-size: 12px;
    margin-top: 0.8vw;
    padding: 4px 10px;
    background: #36d49e;
    color: #ffffff;
    border-radius: 5px;
    margin: 10px;
  }
}
</style>
