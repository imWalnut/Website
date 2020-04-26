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
            <p class="drawerP">首页</p>
            <p class="drawerP">关于我们</p>
            <p class="drawerP">解决方案</p>
            <p class="drawerP">典型案例</p>
            <p class="drawerP">专业服务</p>
          </drawer>
          <div class="logo" :style="this.logoDiv">
            <img :src="this.logoPic" :style="this.logoStyle">
          </div>
          <div class="menu"  v-if="this.pageWidth > 1000">
            <menu mode="horizontal" active-name="1" theme="light">
              <menu-item name="1">
                专业服务
              </menu-item>
              <menu-item name="2">
                典型案例
              </menu-item>
              <menu-item name="3">
                解决方案
              </menu-item>
              <menu-item name="4">
                关于我们
              </menu-item>
              <menu-item name="5">
                首页
              </menu-item>
            </menu>
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
    <div class="main">
      <div class="content-Customize">
      </div>
      <div class="content-solution">
      </div>
      <div class="content-case">
      </div>
      <div class="content-about">
      </div>
      <div class="content-link">
      </div>
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
      //实时获取滚动条位置
      this.scroll = document.documentElement.scrollTop || window.pageYOffset || document.body.scrollTop
      this.setNavStyle()
      this.setBannerStyle()
    },
    //设置nav
    setNavStyle () {
      if (this.scroll < 1) {
        this.navStyle = 'background-color: aliceblue'
      }else {
        this.navStyle = 'background-color: rgba(240,248,255,0.3);'
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
    //设置轮播图
    setBannerStyle () {
      if (this.pageWidth > 1000) {
        this.bannerHeight = 'height:' + this.pageWidth * 0.304 + 'px;'
        this.bannerPic1 = '../.././static/img/carousel/banner_pc1.jpg'
        this.bannerPic2 = '../.././static/img/carousel/banner_pc2.jpg'
        this.bannerPic3 = '../.././static/img/carousel/banner_pc3.jpg'
      } else if (this.pageWidth < 1000 && this.pageWidth > 700) {
        this.bannerHeight = 'height: 500px;'
        this.bannerPic1 = '../.././static/img/carousel/banner_P1.jpg'
        this.bannerPic2 = '../.././static/img/carousel/banner_P2.jpg'
        this.bannerPic3 = '../.././static/img/carousel/banner_P3.jpg'
      } else if (this.pageWidth < 700) {
        this.bannerHeight = 'height: 640px;'
        this.bannerPic1 = '../.././static/img/carousel/banner_M1.jpg'
        this.bannerPic2 = '../.././static/img/carousel/banner_M2.jpg'
        this.bannerPic3 = '../.././static/img/carousel/banner_M3.jpg'
      }
    }
  },
  mounted() {
    this.handleResponsivePage()
  }
}
</script>
<style scoped>
  .header {
    background-color: antiquewhite;
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
    z-index: 2;
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
    z-index: 1;
  }
  .menu {
    position: absolute;
    width: 85%;
    height: 30px;
    left: 0;
    top: 15px;
    z-index: 3;
  }
  .ivu-menu-item {
    width: 100px;
    float: right;
    font-size: 16px;
    font-weight: bolder;
    margin-top: 3px;
    text-align: right;
    color: #2b2e2e;
  }
  .content-Customize {
    height: 690px;
    background-color: cadetblue;
  }
  .content-solution {
    height: 980px;
    background-color: cornsilk;
  }
  .content-case {
    height: 690px;
    background-color: gainsboro;
  }
  .content-about {
    height: 900px;
    background-color: cadetblue;
  }
  .content-link {
    height: 690px;
    background-color: cornsilk;
  }
</style>
