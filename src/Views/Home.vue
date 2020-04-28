<template>
  <div class="entirety">
    <div class="header">
      <Affix>
        <div
          class="nav"
          :style="this.navStyle">
          <div class="drawer">
            <button
              class="drawerIcon"
              v-if="this.pageWidth < 1000"
              @click="Drawer = true">
              <Icon type="md-menu" size="30"/>
            </button>
          </div>
          <drawer
            placement="left"
            :closable="false"
            v-model="Drawer"
            width="250">
            <p class="drawerP">简介</p>
            <p class="drawerP">行业</p>
            <p class="drawerP">产品</p>
            <p class="drawerP">云</p>
            <p class="drawerP">服务</p>
          </drawer>
          <div class="logo" :style="this.logoDiv">
            <img :src="this.logoPic" :style="this.logoStyle">
          </div>
          <div class="menu"  v-if="this.pageWidth > 1000">
            <dropdown
              class="menuList"
              transfer>
              <button class="menuButton">
                服务
              </button>
              <dropdown-menu slot="list">
                <dropdown-item>产品工程服务</dropdown-item>
                <dropdown-item>专业化测试服务</dropdown-item>
                <dropdown-item>一站式BPO服务</dropdown-item>
                <dropdown-item>软件工程服务</dropdown-item>
                <dropdown-item>性能工程服务</dropdown-item>
              </dropdown-menu>
            </dropdown>
            <dropdown class="menuList" transfer>
              <button class="menuButton">
                云
              </button>
              <dropdown-menu slot="list">
                <dropdown-item>云管理服务</dropdown-item>
                <dropdown-item>医疗研究云平台</dropdown-item>
                <dropdown-item>中小企业云平台</dropdown-item>
                <dropdown-item>知识工作自动化</dropdown-item>
                <dropdown-item>教与学智能服务</dropdown-item>
              </dropdown-menu>
            </dropdown>
            <dropdown class="menuList" transfer>
              <button class="menuButton">
                产品
              </button>
              <dropdown-menu slot="list">
                <dropdown-item>医疗健康</dropdown-item>
                <dropdown-item>智能汽车互联</dropdown-item>
                <dropdown-item>平台产品</dropdown-item>
                <dropdown-item>企业应用</dropdown-item>
                <dropdown-item>一体化应用设备</dropdown-item>
              </dropdown-menu>
            </dropdown>
            <dropdown class="menuList" transfer>
              <button class="menuButton">
                行业
              </button>
              <dropdown-menu slot="list">
                <dropdown-item>行业</dropdown-item>
              </dropdown-menu>
            </dropdown>
            <dropdown class="menuList" transfer>
              <button class="menuButton">
                简介
              </button>
              <dropdown-menu slot="list">
                <dropdown-item>公司简介</dropdown-item>
                <dropdown-item>愿景与使命</dropdown-item>
                <dropdown-item>业务架构</dropdown-item>
                <dropdown-item>企业文化</dropdown-item>
                <dropdown-item>工作机会</dropdown-item>
              </dropdown-menu>
            </dropdown>
          </div>
        </div>
      </Affix>
      <div class="carousel">
        <Carousel
          autoplay
          loop
          :autoplay-speed="autoplaySpeed"
          :style="this.bannerHeight">
          <CarouselItem>
            <div class="demo-carousel">
              <img :style="this.bannerHeight" :src="this.bannerPic1">
            </div>
          </CarouselItem>
          <CarouselItem>
            <div class="demo-carousel">
              <img :style="this.bannerHeight" :src="this.bannerPic2">
            </div>
          </CarouselItem>
          <CarouselItem>
            <div class="demo-carousel">
              <img :style="this.bannerHeight" :src="this.bannerPic3">
            </div>
          </CarouselItem>
        </Carousel>
      </div>
    </div>
    <div class="industry">
      <div v-if="this.pageWidth >= 1000">
        <div class="industryBottom">
          <row class="industryRow">
            <i-col span="6" class="bgcLightgrey">
              <a href="#"><img class="industryColPic" src="../.././static/img/industry/dianxin.png"></a>
            </i-col>
            <i-col span="6" class="bgcDarkgrey">
              <div class="industryCol">
                <a href="#"><img class="industryColPic" src="../.././static/img/industry/zhizao.png"></a>
              </div>
            </i-col>
            <i-col span="6" class="bgcLightgrey">
              <div class="industryCol">
                <a href="#"><img class="industryColPic" src="../.././static/img/industry/jinrong.png"></a>
              </div>
            </i-col>
            <i-col span="6" class="bgcDarkgrey">
              <div class="industryCol">
                <a href="#"><img class="industryColPic" src="../.././static/img/industry/keji.png"></a>
              </div>
            </i-col>
          </row>
          <row class="industryRow">
            <i-col span="6" class="bgcDarkgrey">
              <div class="industryCol">
                <a href="#"><img class="industryColPic" src="../.././static/img/industry/yiliao.png"></a>
              </div>
            </i-col>
            <i-col span="6" class="bgcLightgrey"></i-col>
            <i-col span="6" class="bgcDarkgrey"></i-col>
            <i-col span="6" class="bgcLightgrey">
              <div class="industryCol">
                <a href="#"><img class="industryColPic" src="../.././static/img/industry/zhihuichengshi.png"></a>
              </div>
            </i-col>
          </row>
          <row class="industryRow">
            <i-col span="6" class="bgcLightgrey">
              <div class="industryCol">
                <a href="#"><img class="industryColPic" src="../.././static/img/industry/jiaoyu.png"></a>
              </div>
            </i-col>
            <i-col span="6" class="bgcDarkgrey">
              <div class="industryCol">
                <a href="#"><img class="industryColPic" src="../.././static/img/industry/huanbao.png"></a>
              </div>
            </i-col>
            <i-col span="6" class="bgcLightgrey">
              <div class="industryCol">
                <a href="#"><img class="industryColPic" src="../.././static/img/industry/nengyuan.png"></a>
              </div>
            </i-col>
            <i-col span="6" style="background-color: #2e3545; height: 190px; text-align: center">
              <div class="industryCol">
                <a href="#"><img class="industryColPic" src="../.././static/img/industry/more.png"></a>
              </div>
            </i-col>
          </row>
        </div>
        <div class="industryTop">
          <div style="margin-top: 30px">
            <h class="topItem">Industry</h>
            <hr style="width: 100px; height: 1px; background-color: #ffffff; border: 0; margin: 0 auto">
            <h class="topTitle" style="line-height: 100px">面向行业客户的全面解决方案</h>
            <br>
            <div class="topInfo">
              <a>东州科技以210余个业务方向，750种解决方案及产品<br>，支撑电信、能源、金融、IT、医疗、环保等20余个行业的快速发展，<br>推动国民经济基础设施与重要民生领域的信息化水平不断提高。</a>
            </div>
          </div>
        </div>
      </div>
      <div v-else-if="this.pageWidth < 1000 && this.pageWidth > 700"></div>
      <div v-else-if="this.pageWidth <= 700"></div>
    </div>
    <div class="product">
      <div class="productHeader">
        <h class="topItem">Product</h>
        <hr style="width: 100px; height: 1px; background-color: #ffffff; border: 0; margin: 0 auto">
        <p style="line-height: 30px; background-color: white; width: 300px; margin: 0 auto; margin-top: 20px; border-radius: 30px; color: #2a7cd0">全面支撑客户数字化转型与智能化运营</p>
      </div>
      <div class="productMain" v-if="this.pageWidth >= 1000">
        <row class="productMainRowPc">
          <i-col span="6" class="productMainColPc">
            <div style="height: 200px">
              <button class="productMainButton">
                <img class="productMainButton" src="../.././static/img/product/jituancaiwu.jpg">
                <a class="productMainItemPc">集团财务管控</a>
                <hr style="width: 20px; height: 3px; background-color: #ffffff; border: 0; margin: 0 auto">
              </button>
            </div>
            <div style="height: 120px; width: 200px; margin: 0 auto">
              <h class="topInfo">资金管理平台、银企协同平台、报账管理平台、财务共享运营平台、财税管理平台>></h>
            </div>
          </i-col>
          <i-col span="6" class="productMainColPc">
            <div style="height: 200px">
              <button class="productMainButton">
                <img class="productMainButton" src="../.././static/img/product/rencaiziben.jpg">
                <a class="productMainItemPc">人才资本管理</a>
                <hr style="width: 20px; height: 3px; background-color: #ffffff; border: 0; margin: 0 auto">
              </button>
            </div>
            <div style="height: 120px; width: 200px; margin: 0 auto">
              <h class="topInfo">定向解决大中型企业、复杂用工关系和复杂结构组织、协同业务模式下的全面人才管理>></h>
            </div>
          </i-col>
          <i-col span="6" class="productMainColPc">
            <div style="height: 200px">
              <button class="productMainButton">
                <img class="productMainButton" src="../.././static/img/product/dashujufenxi.jpg">
                <a class="productMainItemPc">大数据分析</a>
                <hr style="width: 20px; height: 3px; background-color: #ffffff; border: 0; margin: 0 auto">
              </button>
            </div>
            <div style="height: 120px; width: 200px; margin: 0 auto">
              <h class="topInfo">聚焦客户智能、IoT智能与运营智能领域，降低大数据分析工作的难度，发掘数据深层价值>></h>
            </div>
          </i-col>
          <i-col span="6" class="productMainColPc">
            <div style="height: 200px">
              <button class="productMainButton">
                <img class="productMainButton" src="../.././static/img/product/shipinjiancha.jpg">
                <a class="productMainItemPc">视频监察</a>
                <hr style="width: 20px; height: 3px; background-color: #ffffff; border: 0; margin: 0 auto">
              </button>
            </div>
            <div style="height: 120px; width: 200px; margin: 0 auto">
              <h class="topInfo">前端采集设备作为“眼睛”，中心端视频结构化分析、精准的图像识别和大数据分析作为“大脑”>></h>
            </div>
          </i-col>
        </row>
        <row class="productMainRowPc">
          <i-col span="6" class="productMainColPc">
            <div style="height: 200px">
              <button class="productMainButton">
                <img class="productMainButton" src="../.././static/img/product/wangluoanquan.jpg">
                <a class="productMainItemPc">网络安全产品</a>
                <hr style="width: 20px; height: 3px; background-color: #ffffff; border: 0; margin: 0 auto">
              </button>
            </div>
            <div style="height: 120px; width: 200px; margin: 0 auto">
              <h class="topInfo">提供成熟、先进的网络安全产品以及高效、完善的安全解决方案与服务>></h>
            </div>
          </i-col>
          <i-col span="6" class="productMainColPc">
            <div style="height: 200px">
              <button class="productMainButton">
                <img class="productMainButton" src="../.././static/img/product/zhinengqiche.jpg">
                <a class="productMainItemPc">智能汽车互联</a>
                <hr style="width: 20px; height: 3px; background-color: #ffffff; border: 0; margin: 0 auto">
              </button>
            </div>
            <div style="height: 120px; width: 200px; margin: 0 auto">
              <h class="topInfo">致力于打造出安全、舒适、绿色的汽车生态系统和移动出行服务>></h>
            </div>
          </i-col>
          <i-col span="6" class="productMainColPc">
            <div style="height: 200px">
              <button class="productMainButton">
                <img class="productMainButton" src="../.././static/img/product/yilianjiankang.jpg">
                <a class="productMainItemPc">医疗健康产品</a>
                <hr style="width: 20px; height: 3px; background-color: #ffffff; border: 0; margin: 0 auto">
              </button>
            </div>
            <div style="height: 120px; width: 200px; margin: 0 auto">
              <h class="topInfo">消除信息孤岛，提升患者服务水平、提高医护工作效率、增强医疗质量、降低运行成本>></h>
            </div>
          </i-col>
          <i-col span="6" class="productMainColPc">
            <div style="height: 200px">
              <button class="productMainButton">
                <img class="productMainButton" src="../.././static/img/product/yitihuayingyong.jpg">
                <a class="productMainItemPc">一体化应用</a>
                <hr style="width: 20px; height: 3px; background-color: #ffffff; border: 0; margin: 0 auto">
              </button>
            </div>
            <div style="height: 120px; width: 200px; margin: 0 auto">
              <h class="topInfo">智能自助终端系列产品、企业智能终端系列产品、智慧统一服务平台>></h>
            </div>
          </i-col>
        </row>
      </div>
      <div v-else-if="this.pageWidth < 1000 && this.pageWidth > 700"></div>
      <div v-else-if="this.pageWidth <= 700"></div>
      <div class="productFootPc">
        <button style="height: 43px; width: 43px; border: 0; border-radius: 21px; cursor: pointer; outline: none">
          <img src="../.././static/img/product/s2-more.png">
        </button>
      </div>
    </div>
    <div class="serve">
    </div>
    <div class="about">
    </div>
    <div class="footer">
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      scroll: 0,
      pageWidth: document.documentElement.clientWidth,
      navStyle: '',
      logoPic: '',
      logoStyle: '',
      logoDiv: '',
      Drawer: false,
      autoplaySpeed: 5000,
      bannerHeight: '',
      bannerStyle: '',
      bannerPic1: '',
      bannerPic2: '',
      bannerPic3: '',
      industryStyle: '',
    }
  },
  created() {
    window.addEventListener('resize', this.handleResponsivePage)
    window.addEventListener("scroll", this.handleResponsivePage);
  },
  beforeDestroy: function () {
    window.removeEventListener('resize', this.handleResponsivePage)
    window.removeEventListener("scroll", this.handleResponsivePage);
  },
  methods: {
    //响应式页面
    handleResponsivePage () {
      //实时获取页面宽度
      this.pageWidth = document.documentElement.clientWidth
      console.log(this.pageWidth)
      //实时获取滚动条位置
      this.scroll = document.documentElement.scrollTop || window.pageYOffset || document.body.scrollTop
      this.$nextTick()
      this.setHeaderNav()
      this.setHeaderBanner()
      this.setindustry()
    },
    //nav
    setHeaderNav () {
      if (this.scroll < 1) {
        this.navStyle = 'background-color: aliceblue'
      }else {
        this.navStyle = 'background-color: rgba(240,248,255,0.5);'
      }
      this.logoPic = '../.././static/img/EastState.png'
      if (this.pageWidth > 1000) {
        this.logoStyle = 'margin-left: 15%'
        this.logoDiv = ''
      }else {
        this.logoStyle = ''
        this.logoDiv = 'text-align: center;'
      }
    },
    //轮播图
    setHeaderBanner () {
      if (this.pageWidth >= 1000) {
        this.bannerHeight = 'height:' + this.pageWidth * 0.304 + 'px;'
        this.bannerPic1 = '../.././static/img/carousel/banner_pc1.jpg'
        this.bannerPic2 = '../.././static/img/carousel/banner_pc2.jpg'
        this.bannerPic3 = '../.././static/img/carousel/banner_pc3.jpg'
      } else if (this.pageWidth < 1000 && this.pageWidth > 700) {
        this.bannerHeight = 'height: 500px;'
        this.bannerPic1 = '../.././static/img/carousel/banner_P1.jpg'
        this.bannerPic2 = '../.././static/img/carousel/banner_P2.jpg'
        this.bannerPic3 = '../.././static/img/carousel/banner_P3.jpg'
      } else if (this.pageWidth <= 700) {
        this.bannerHeight = 'height: 640px;'
        this.bannerPic1 = '../.././static/img/carousel/banner_M1.jpg'
        this.bannerPic2 = '../.././static/img/carousel/banner_M2.jpg'
        this.bannerPic3 = '../.././static/img/carousel/banner_M3.jpg'
      }
    },
    // 行业模块
    setindustry () {
    },
  },
  mounted() {
    this.handleResponsivePage()
  }
}
</script>
<style>
  a:hover {
    color: peachpuff;
  }
  .header {
    position:relative;
  }
  .carousel {
  }
  .nav {
    height: 60px;
    position:relative;
    overflow: hidden;
  }
  .drawer {
    position: absolute;
    width: 60px;
    height: 60px;
    background-color: transparent;
    z-index: 3;
  }
  .drawerIcon {
    border: 0;
    background-color: transparent;
    margin-top: 15px;
    margin-left: 15px;
  }
  .drawerP {
    color: #2b2e2e;
    margin: 35px 0px 0px 40px;
    font-size: 16px;
  }
  .logo {
    position: absolute;
    background-color: transparent;
    width: 100%;
    height: 40px;
    left: 0;
    top: 10px;
    z-index: 2;
  }
  .menu {
    position: absolute;
    width: 85%;
    height: 30px;
    left: 0;
    top: 15px;
    z-index: 4;
  }
  .menuList {
    width: 100px;
    height: 30px;
    background-color: transparent;
    border: 0;
    margin: 0;
    padding: 0;
    float: right;
    text-align: center;
  }
  .ivu-select-dropdown {
    margin-top: 15px;
    max-height: 300px;
    border-radius: 0px;
    background-color: rgba(240,248,255,0.3);
    font-family: "Microsoft YaHei";
    font-weight: bold;
  }
  .ivu-dropdown-item {
    color: #2b2e2e;
  }
  .menuButton {
    width: 100px;
    height: 30px;
    font-family: "Microsoft YaHei";
    font-size: 16px;
    font-weight: bolder;
    cursor: pointer;
    border: 0;
    background-color: transparent;
    outline: none;
  }

  .industry {
    height: 690px;
    overflow: hidden;
    position: relative;
  }
  .industryBottom {
    height: 570px;
    width: 80%;
    margin-left: 10%;
    margin-top: 60px;
  }
  .industryRow {
    height: 190px;
  }
  .bgcDarkgrey {
    background-color: #ECECEC;
    height: 190px;
    text-align: center;
  }
  .bgcLightgrey {
    background-color: #f9f9f9;
    height: 190px;
    text-align: center;
  }
  .industryColPic {
    width: 70px;
    height: 70px;
    margin-top: 60px;
  }
  .industryTop {
    position: absolute;
    top: 200px;
    width: 46%;
    margin-left: 27%;
    height: 290px;
    background-image: url("../.././static/img/industry/s1-item2.jpg");
    background-repeat: no-repeat;
    background-size: 100% 290px;
    text-align: center;
  }
  .topItem {
    color: white;
    font-size: 30px;
    line-height: 50px;
    font-weight: bolder;
    font-family: 'Microsoft YaHei'
  }
  .topTitle {
    color: white;
    font-size: 35px;
  }
  .topInfo {
    width: 450px;
    margin: 0 auto;
    color: white
  }
  .product {
    width: 100%;
    height: 940px;
    position: absolute;
    background-image: url("../.././static/img/product/s2-bg.jpg");
    background-repeat: no-repeat;
    background-size: 100% 1060px;
  }
  .productHeader {
    width: 100%;
    height: 130px;
    margin: 60px 0 0 0;
    text-align: center;
  }
  .productMain {
    width: 80%;
    height: 670px;
    margin-left: 10%;
  }
  .productMainRowPc {
    width: 100%;
    height: 320px;
    top: 30px;
    text-align: center;
  }
  .productMainColPc {
    height: 320px;
  }
  .productMainButton {
    width: 120px;
    height: 120px;
    border-radius: 60px;
    border: 0;
    outline: none;
    cursor: pointer
  }
  .productMainItemPc {
    font-size: 20px;
    color: white;
    font-weight: bold;
    font-family: 'Microsoft YaHei';
    line-height: 50px
  }
  .productFootPc {
    width: 100%;
    height: 90px;
    text-align: center;
  }
</style>
