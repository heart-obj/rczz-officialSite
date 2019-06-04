<template>
  <div>
    <div class="box1">
      <div class="text-title1">About US</div>
      <div class="text-title2">
        <span class="line line1"></span>
        <span class="text">关于我们</span>
        <span class="line line2"></span>
      </div>
      <div class="text-title3">优质团队为您服务</div>
      <div class="row pc-row">
        <div class="col-6">
          <div class="aboutus-img-box">
            <div class="aboutus-img"
            v-for="(item, index) in imglist"
            :key="index"
            :class="index % 2 !== 0 ? 'aboutus-img2' : ''"
            :style="{'background': 'url('+ item +')no-repeat center'}"></div>
          </div>
        </div>
        <div class="col-6 col-ms-10">
          <div>
            <div class="aboutus-title aboutus-title1">公司简介</div>
            <div class="aboutus-text">
              我们是由中软国际（http://www.chinasofti.com/）和华为技术有限公司（http://www.huawei.com/）的研发人员发起成立，经过8年多的不懈努力，我们已经成长为一个同时具备设计部，研发部，代办服务部，市场部的高新技术企业。业务遍及中国内地、港台、新加坡、柬埔寨、美国和英国等，服务过300多个客户，并有近10款软件成功获得投资、融资。我们始终坚持做就一定要做好的口号，以做产品的态度和经营理念，一路上获得了众多客户的好评和长期合作。作为一个创业型企业，我们深知为客户做的每一款产品，都承载着客户的梦想，甚至关乎着客户的未来。基于此，我们对产品提出了严苛的要求，我们不只是帮助客户开发产品，我们更想通过我们的前沿行业信息，尽可能的为客户提供一切与产品有关的帮助。我们希望能成为每一位客户最贴心、最放心的长期合作伙伴！<br/>
              在承接外包项目合作方面，我们始终坚持打造成为一支致力于为全球客户提供优质的一站式服务供应商。以“do it well if you do it at all !”(做就一定要做好！)为服务宗旨，始终坚持客户满意为最终目标，并以产品的心态提供优质服务助力客户成功！
            </div>
          </div>
          <div>
            <div class="aboutus-title aboutus-title2">团队培养</div>
            <div style="margin-top: 1vw;" v-for="(item, index) in textlist" :key="index">
              <div class="col-h" v-html="item.title"></div>
              <div class="aboutus-text" style="margin-top: 10px;" v-html="item.text"></div>
            </div>
          </div>
        </div>
      </div>
      <div class="mobile-row">
        <div class="row justify-content-start">
          <div class="col-sm-6 rowCol">
            <div class="aboutus-img-box">
              <div class="aboutus-img"
              v-for="(item, index) in imglist"
              :key="index"
              :class="index % 2 !== 0 ? 'aboutus-img2' : ''"
              :style="{'background': 'url('+ item +')no-repeat center'}"></div>
            </div>
          </div>
          <div class="col-sm-6 rowCol">
            <div>
              <div class="aboutus-title aboutus-title1">公司简介</div>
              <div class="aboutus-text">
                我们是由中软国际（http://www.chinasofti.com/）和华为技术有限公司（http://www.huawei.com/）的研发人员发起成立，经过8年多的不懈努力，我们已经成长为一个同时具备设计部，研发部，代办服务部，市场部的高新技术企业。业务遍及中国内地、港台、新加坡、柬埔寨、美国和英国等，服务过300多个客户，并有近10款软件成功获得投资、融资。我们始终坚持做就一定要做好的口号，以做产品的态度和经营理念，一路上获得了众多客户的好评和长期合作。作为一个创业型企业，我们深知为客户做的每一款产品，都承载着客户的梦想，甚至关乎着客户的未来。基于此，我们对产品提出了严苛的要求，我们不只是帮助客户开发产品，我们更想通过我们的前沿行业信息，尽可能的为客户提供一切与产品有关的帮助。我们希望能成为每一位客户最贴心、最放心的长期合作伙伴！<br/>
                在承接外包项目合作方面，我们始终坚持打造成为一支致力于为全球客户提供优质的一站式服务供应商。以“do it well if you do it at all !”(做就一定要做好！)为服务宗旨，始终坚持客户满意为最终目标，并以产品的心态提供优质服务助力客户成功！
              </div>
            </div>
          </div>
        </div>
        <div style="display:inline-block;padding: 0 15px;">
          <div>
            <div class="aboutus-title aboutus-title2" >团队培养</div>
          </div>
          <div style="margin-top: 1vw;" v-for="(item, index) in textlist" :key="index">
            <div class="col-h" v-html="item.title"></div>
            <div class="aboutus-text" style="margin-top: 10px;" v-html="item.text"></div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'Aboutus', // 关于我们
  data () {
    return {
      imglist: [ './static/img/photo1.png', './static/img/photo2.png', './static/img/photo3.png', './static/img/photo4.png' ],
      textlist: [
        {
          title: '团队文化-<span style="font-size: 1.6vw;font-weight: 600;color: #333">狼性文化</span>',
          text: '创始人最崇敬华为科技的狼性文化，以任正非为榜样。对团队要求始终坚持：要么不做，要做就一定做好！'
        },
        {
          title: '团队氛围-<span style="font-size: 1.6vw;font-weight: 600;color: #333">和谐融洽</span>',
          text: '因为我们都是一群年轻人，整个公司没有严重的上下级氛围，大家都以兄弟姐妹看待。所以团队氛围和谐、关系融洽。'
        },
        {
          title: '团队理念-<span style="font-size: 1.6vw;font-weight: 600;color: #333">高效率  强执行</span>',
          text: '作为以外包为核心业务的公司，市场竞争压力显而易见。没有高效率就没有盈利，而高效率又出自强执行力。因此公司注重效率的提升，主张“立即行动”。不管是公司管理还是项目开展过程中，都减少不必要的中间环节。'
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
.row {
  width: 100%;
  margin: auto;
}
.row>>>div {
  box-sizing: border-box;
}
.aboutus-img-box {
  display: inline-block;
  margin-top: 8vw;
}
.aboutus-img {
  width: 16.8vw;
  height: 9.45vw;
  background-size: 100% 100% !important;
  display: block;
  margin-top: -2vw;
}
.aboutus-img2 {
  margin-left: 14vw;
  margin-top: -7vw;
}
.aboutus-title {
  font-size: 1.875vw;
  color: #333333;
  font-weight: 600;
  position: relative;
  margin-bottom: 20px;
  padding-top: 20px;
}
.aboutus-title1 {
  background: url('./img/Companyprofile.png') no-repeat center;
  background-position: center 0px;
}
.aboutus-title2 {
  padding-top: 40px;
  background: url('./img/TeamIntroduction.png') no-repeat center;
  background-position: center 20px;
}
.aboutus-title::after {
  content: '';
  display: inline-block;
  width: 36px;
  height: 5px;
  position: absolute;
  bottom: -8px;
  left: 0;
  right: 0;
  margin: 0 auto;
  background: #499aff;
  border-radius: 5px;
}
.aboutus-text {
  font-size: 14px;
  color: #666666;
  text-align: left;
  padding: 0 15px;
}
.col-h {
  text-align: left;
  color: #333333;
  font-size: 1.6vw;
  position: relative;
  padding-left: 20px;
}
.col-h::after {
  content: '';
  display: inline-block;
  width: 10px;
  height: 10px;
  position: absolute;
  top: 0;
  bottom: 0;
  left: 0px;
  margin: auto;
  background: #499aff;
  border-radius: 5px;
}
.mobile-row {
  display: none;
}
.rowCol {
  display: inline-block;
  width: 50%;
}
@media screen and (max-width: 1200px) {
  .pc-row {
    display: none;
  }
  .mobile-row{
    display: inline-block;
  }
  .aboutus-img-box {
    display: inline-block;
    margin-top: 2vw;
  }
  .aboutus-img {
    width: 200px;
    height: 150px;
    background-size: 100% 100% !important;
    display: block;
  }
}
@media screen and (max-width: 600px) {
  .rowCol {
    display: block;
    width: 100%;
    margin-bottom: 20px;
    padding: 0;
  }
  .mobile-row{
    display: inline-block;
    padding: 0;
  }
  .aboutus-img-box {
    display: inline-block;
    margin-top: 2vw;
  }
  .aboutus-img {
    width: 280px;
    height: 190px;
    background-size: 100% 100% !important;
    display: block;
  }
}
</style>
