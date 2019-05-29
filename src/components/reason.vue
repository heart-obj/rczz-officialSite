<template>
  <div>
    <div class="box1">
      <div class="text-title1">Reason to choose us</div>
      <div class="text-title2">
        <span class="line line1"></span>
        <span class="text">选择我们的理由</span>
        <span class="line line2"></span>
      </div>
      <div class="text-title3">优势和实力让您信任</div>
      <div class="text-title4">
        9年多项目开发，我们拥有合理且高效的项目管理机制；300多款成功案例，凝聚了经验丰富的研发团队。“要么不做，要么做好”的公司理念根植于每一位极越人心中。
      </div>
      <div class="icons">
        <div class="icon"></div>
        <div class="icon"></div>
        <div class="icon"></div>
      </div>
      <h5 style="color:#000;font-weight:bold;">您的烦恼</h5>
      <div class="row-box">
        <div class="col-box">
          <div class="col-row">
            <div class="col-div col-div1">
              <span class="triangle-right"></span>
              <div style="width: 100%;height: 50%;padding: 15px 30px;font-size: 0.93vw;color: #999999">项目需求模糊缺乏专业的人梳理</div>
              <div style="width: 100%;height: 50%;" :style="{background: 'url('+ iconurl[0] +') no-repeat center','background-size': '100% 100%'}"></div>
            </div>
            <div class="col-div">
              <div class="title-div">“</div>
              <span class="text-col">我们有专业的产品经理为您梳理需求</span>
            </div>
          </div>
          <div class="col-row">
            <div class="col-div">
              <div class="title-div">“</div>
              <span class="text-col">我们的开发速度很快 落地效果好</span>
            </div>
            <div class="col-div col-div1">
              <span class="triangle-left"></span>
              <div style="width: 100%;height: 50%;padding: 15px 30px;font-size: 0.93vw;color: #999999">工期紧时间太赶 项目效果差</div>
              <div style="width: 100%;height: 50%;" :style="{background: 'url('+ iconurl[4] +') no-repeat center','background-size': '100% 100%'}"></div>
            </div>
          </div>
        </div>
        <div class="col-box">
          <div class="col-row">
            <div class="col-div col-div1">
              <span class="triangle-right"></span>
              <div style="width: 100%;height: 50%;padding: 15px 30px;font-size: 0.93vw;color: #999999">项目自建技术团队 成本太高</div>
              <div style="width: 100%;height: 50%;" :style="{background: 'url('+ iconurl[1] +') no-repeat center','background-size': '100% 100%'}"></div>
            </div>
            <div class="col-div">
              <div class="title-div">“</div>
              <span class="text-col">我们有优秀的技术团队 物美价优</span>
            </div>
          </div>
          <div class="col-row">
            <div class="col-div">
              <div class="title-div">“</div>
              <span class="text-col">我们的技术质量过关 让您运营无忧</span>
            </div>
            <div class="col-div col-div1">
              <span class="triangle-left"></span>
              <div style="width: 100%;height: 50%;padding: 15px 30px;font-size: 0.93vw;color: #999999">不懂技术管理 产品难运营</div>
              <div style="width: 100%;height: 50%;" :style="{background: 'url('+ iconurl[4] +') no-repeat center','background-size': '100% 100%'}"></div>
            </div>
          </div>
        </div>
        <div class="col-box2">
          <div class="col-row2">
            <div class="col-div col-div1">
              <span class="triangle-bottom"></span>
              <div style="width: 100%;height: 50%;" :style="{background: 'url('+ iconurl[2] +') no-repeat center','background-size': '100% 100%'}"></div>
              <div style="width: 100%;height: 50%;padding: 15px 30px;font-size: 0.93vw;color: #999999">服务商报价五花八门 价格悬殊太大</div>
            </div>
            <div class="col-div">
              <div class="title-div">“</div>
              <span class="text-col">我们的报价清单罗列 合情合理</span>
            </div>
          </div>
        </div>
      </div>
      <div class="mobilerow-box">
        <div class="col-box" v-for="(item, index) in mobileList" :key="index">
          <div class="col-row" v-if="index % 2 === 0">
            <div class="col-div col-div1">
              <span class="triangle-right"></span>
              <div style="width: 100%;height: 50%;padding: 15px 30px;font-size: 16px;color: #999999">{{ item.title }}</div>
              <div style="width: 100%;height: 50%;" :style="{background: 'url('+ item.bgimgUrl +') no-repeat center','background-size': '100% 100%'}"></div>
            </div>
            <div class="col-div">
              <div class="title-div">“</div>
              <span class="text-col">{{ item.text }}</span>
            </div>
          </div>
          <div class="col-row" v-else>
            <div class="col-div">
              <div class="title-div">“</div>
              <span class="text-col">{{ item.text }}</span>
            </div>
            <div class="col-div col-div1">
              <span class="triangle-left"></span>
              <div style="width: 100%;height: 50%;padding: 15px 30px;font-size: 16px;color: #999999">{{ item.title }}</div>
              <div style="width: 100%;height: 50%;" :style="{background: 'url('+ item.bgimgUrl +') no-repeat center','background-size': '100% 100%'}"></div>
            </div>
          </div>
        </div>
      </div>
      <div class="icons">
        <div class="icon"></div>
        <div class="icon"></div>
        <div class="icon"></div>
      </div>
      <h5 style="color:#000;font-weight:bold;">我们的优势</h5>
      <div class="swiper-box">
        <swiper :options="swiperOption">
          <swiper-slide v-for="(item, i) in swiperContent" :key="i">
            <div class="swiper-col" :style="{'background': 'url('+ item.bgimgUrl +')no-repeat center','background-size': '100% 100%'}">
              <header class="swiper-h">
                <span class="left-line"></span>
                {{item.headerText}}
                <span class="right-line"></span>
              </header>
              <div class="title-div">“</div>
              <span class="swiper-text">{{item.label}}</span>
            </div>
          </swiper-slide>
        </swiper>
        <p class="swiper-pagination"  v-for="(item,index) in swiperContent" :key="index" slot="pagination" ></p>
      </div>
    </div>
  </div>
</template>
<script>
import 'swiper/dist/css/swiper.css'
import { swiper, swiperSlide } from 'vue-awesome-swiper'
export default {
  name: 'Reason', // 选择我们的理由
  components: {
    swiper,
    swiperSlide
  },
  data () {
    return {
      iconurl: [
        './static/img/pic1.png',
        './static/img/pic2.png',
        './static/img/pic3.png',
        './static/img/pic4.png',
        './static/img/pic5.png'
      ],
      swiperOption: {
        // delay: 1000,
        autoplay: {
          // disableOnInteraction: false
        },
        speed: 1000,
        loop: true,
        effect: 'coverflow',
        pagination: {
          el: '.swiper-pagination',
          type: 'bullets',
          clickable: true
        }
      },
      swiperContent: [
        {
          label: '公司已经历经8年多的奋斗，研发了超200款中大型软件项目，并且近10款软件的客户获得投资融资，公司明确要求不仅不招实习生、应届生，而且必须要有至少3年相关领域经验的求职者，才有面试资格。在通过面试并入职一周内为观察期，合格者才会签订劳动合同。团队每一位成员代码量平均每天800行。',
          headerText: '技术过硬  经验丰富',
          bgimgUrl: './static/img/swiper1.png'
        },
        {
          label: '公司明确要求不仅不招实习生、应届生，而且必须要有至少3年相关领域经验的求职者，才有面试资格。在通过面试并入职一周内为观察期，合格者才会签订劳动合同。',
          headerText: '强大的技术实力',
          bgimgUrl: './static/img/swiper2.png'
        },
        {
          label: '公司明确要求不仅不招实习生、应届生，而且必须要有至少3年相关领域经验的求职者，才有面试资格。在通过面试并入职一周内为观察期，合格者才会签订劳动合同。',
          headerText: '强大的技术实力',
          bgimgUrl: './static/img/swiper3.png'
        }
      ],
      mobileList: [
        {
          title: '项目需求模糊缺乏专业的人梳理',
          bgimgUrl: './static/img/pic1.png',
          text: '我们有专业的产品经理 为您梳理需求'
        },
        {
          title: '项目自建技术团队成本太高',
          bgimgUrl: './static/img/pic2.png',
          text: '我们优秀的技术团队 物美价优'
        },
        {
          title: '服务商报价五花八门价格悬殊太大',
          bgimgUrl: './static/img/pic3.png',
          text: '我们的报价清单罗列 合情合理'
        },
        {
          title: '不懂技术管理产品难运营',
          bgimgUrl: './static/img/pic4.png',
          text: '我们的技术质量过关 让您运营无忧'
        },
        {
          title: '工期时间太赶项目效果差',
          bgimgUrl: './static/img/pic5.png',
          text: '我们的开发速度很快 落地效果好'
        }
      ]
    }
  },
  methods: {
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
  width: calc(50% - 140px);
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
.icons {
  margin: 1.1vw 0;
}
.icons .icon {
  width: 7px;
  height: 7px;
  border-radius: 7px;
  background: rgba(220, 220, 220, 1);
  margin: 5px auto;
}
.row-box {
  margin: 4vw 0;
  display: inline-block;
  text-align: center;
  font-size: 0;
  -webkit-text-size-adjust:none;
}
.row-box>div {
  display: inline-block;
}
.row-box .col-box {
  width: 25vw;
  height: 19.79vw;
}
.row-box .col-box2 {
  width: 12.5vw;
  height: 19.79vw;
}
.col-row {
 width: 100%;
 height: 50%;
}
.col-row .col-div {
  width: 50%;
  height: 100%;
  float: left;
  background: #ffffff;
  position: relative;
}
.col-div .title-div {
  color: #333333;
  font-weight: bold;
  font-size: 4.1vw;
  line-height: 5.1vw;
}
.col-div .text-col {
  color: #333333;
  font-weight: bold;
  font-size: 1.1vw;
  padding: 0 10px;
}
.col-row .col-div1 {
  background: #ebebeb;
}
.col-row2 {
  width: 100%;
  height: 100%;
  float: left;
}
.col-row2 .col-div {
  width: 100%;
  height: 50%;
  background: #ffffff;
  position: relative;
}
.col-row2 .col-div1 {
  background: #ebebeb;
}
.triangle-right {
  display: block;
  width: 0;
  height: 0;
  border-width: 15px 0 15px 15px;
  border-style: solid;
  border-color: transparent transparent transparent #ebebeb;
  position: absolute;
  top: 18px;
  right: -14px;
  z-index: 11
}
.triangle-left {
  display: block;
  width: 0;
  height: 0;
  border-width: 15px 15px 15px 0;
  border-style: solid;
  border-color: transparent #ebebeb transparent transparent;
  position: absolute;
  top: 18px;
  left: -14px;
  z-index: 11
}
.triangle-bottom {
  display: block;
  width: 0;
  height: 0;
  border-width: 15px 15px 0;
  border-style: solid;
  border-color:#ebebeb transparent transparent;
  position: absolute;
  bottom: -14px;
  left: 0;
  right: 0;
  margin: auto;
  z-index: 11
}
.swiper-box {
  display: inline-block;
  width: 62.5vw;
  height: 23.4vw;
  position: relative;
}
.swiper-col {
  display: inline-block;
  width: 44.95vw;
  height: 23.4vw;
  border-radius: 10px;
  box-shadow: 0 5px 20px rgba(0, 0, 0, .5);
}
.swiper-col .swiper-h {
  font-size: 1.875vw;
  padding: 2.6vw 0;
  position: relative;
}
.swiper-col .swiper-h::after {
  position: absolute;
  left: 0.52vw;
  top: 0;
  bottom: 0;
  margin: auto;
  content: '';
  display: inline-block;
  width: 11.8vw;
  height: 1px;
  background: #ffffff;
}
.swiper-col .swiper-h .left-line{
  position: absolute;
  left: 4.32vw;
  top: 0;
  bottom: 0;
  margin: auto;
  content: '';
  display: inline-block;
  width: 8vw;
  height: 5px;
  background: #ffffff;
  border-radius: 5px;
  z-index: 11;
}
.swiper-col .swiper-h::before {
  position: absolute;
  right: 0.52vw;
  top: 0;
  bottom: 0;
  margin: auto;
  content: '';
  display: inline-block;
  width: 11.8vw;
  height: 1px;
  background: #ffffff;
}
.swiper-col .swiper-h .right-line{
  position: absolute;
  right: 4.32vw;
  top: 0;
  bottom: 0;
  margin: auto;
  content: '';
  display: inline-block;
  width: 8vw;
  height: 5px;
  background: #ffffff;
  border-radius: 5px;
  z-index: 11;
}
.swiper-col .title-div {
  color: #ffffff;
  font-weight: bold;
  font-size: 4.1vw;
  line-height: 5.1vw;
}
.swiper-col .swiper-text {
  display: inline-block;
  font-size: 1.25vw;
  color: #ffffff;
  padding: 10px 50px;
}

.swiper-pagination {
  position: absolute;
  left: 0;
  right: 0;
  margin:  10px auto;
}
.swiper-box>.swiper-pagination>>>.swiper-pagination-bullet {
  display: inline-block;
  margin: 0 5px;
  width: 30px;
  height: 8px;
  border-radius: 8px;
  background: rgba(16, 159, 253, .26)

}
.swiper-box>.swiper-pagination>>>.swiper-pagination-bullet-active {
  width: 40px;
  height: 8px;
  border-radius: 8px;
  background: rgba(16, 159, 253, 1)
}
@media (min-width: 768px) {
  .row-box {
    width: 100%;
    display: inline-block;
  }
  .mobilerow-box {
    width: 100%;
    display: none;
  }
}
@media (max-width: 768px) {
  .row-box {
    width: 100%;
    display: none;
  }
  .mobilerow-box {
    width: 100%;
    display: inline-block;
  }
  .mobilerow-box {
    margin: 4vw 0;
    display: inline-block;
    text-align: center;
    font-size: 0;
    -webkit-text-size-adjust:none;
  }
  .mobilerow-box>div {
    display: inline-block;
  }
  .mobilerow-box .col-box {
    width: 100%;
    height: 35vw;
  }
  .mobilerow-box .col-box2 {
    width: 100%;
    height: 35vw;
  }
  .mobilerow-box .col-row {
    height: 100%;
  }
  .triangle-right {
    display: block;
    width: 0;
    height: 0;
    border-width: 15px 0 15px 15px;
    border-style: solid;
    border-color: transparent transparent transparent #ebebeb;
    position: absolute;
    top: 0;
    bottom: 0;
    right: -14px;
    margin: auto;
    z-index: 11
  }
  .triangle-left {
    display: block;
    width: 0;
    height: 0;
    border-width: 15px 15px 15px 0;
    border-style: solid;
    border-color: transparent #ebebeb transparent transparent;
    position: absolute;
    top: 0;
    bottom: 0;
    left: -14px;
    margin: auto;
    z-index: 11
  }
  .col-div .title-div {
    color: #333333;
    font-weight: bold;
    font-size: 60px;
    line-height: 60px;
    padding-top: 20px;
  }
  .col-div .text-col {
    display: inline-block;
    box-sizing: border-box;
    color: #333333;
    font-weight: bold;
    font-size: 3.2vw;
    padding: 0 20px;
  }
  .swiper-box {
    display: inline-block;
    width: 100%;
    position: relative;
  }
  .swiper-col {
    width: 80%;
    height: auto;
  }
  .swiper-col .swiper-text {
    display: inline-block;
    font-size: 1.25vw;
    color: #ffffff;
    padding: 10px;
  }
}
</style>
