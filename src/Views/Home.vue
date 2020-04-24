<template>
  <div class="entirety">
    <div class="header">
      <Affix>
        <div
          class="menu"
          :style="this.menuHeight">
        </div>
      </Affix>
      <div class="carousel">
        <Carousel
          autoplay
          loop
          :style="this.bannerHeight">
          <CarouselItem>
            <div class="demo-carousel"><img :style="this.bannerHeight" src="../.././static/img/carousel/banner1.jpg"></div>
          </CarouselItem>
          <CarouselItem>
            <div class="demo-carousel"><img :style="this.bannerHeight" src="../.././static/img/carousel/banner2.jpg"></div>
          </CarouselItem>
          <CarouselItem>
            <div class="demo-carousel"><img :style="this.bannerHeight" src="../.././static/img/carousel/banner3.jpg"></div>
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
      menuHeight: '',
      bannerHeight: '',
      bannerStyle: ''
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
      //定义menu、轮播图样式
      if (this.scroll < 1 && this.pageWidth > 1100) {
        this.menuHeight = 'height: 80px; background-color: aquamarine'
        this.bannerHeight = 'height:' + this.pageWidth * 0.304 + 'px;'
      }else if (this.scroll > 1 && this.pageWidth > 1100) {
        this.menuHeight = 'height: 60px; background-color: burlywood'
        this.bannerHeight = 'height:' + this.pageWidth * 0.304 + 'px;'
      }else if (this.scroll < 1 && this.pageWidth < 1100 && this.pageWidth > 700) {
        this.menuHeight = 'height: 60px; background-color: aquamarine;'
        this.bannerHeight = 'height: 500px;'
      }else if (this.scroll > 1 && this.pageWidth < 1100 && this.pageWidth > 700) {
        this.menuHeight = 'height: 60px; background-color: burlywood;'
        this.bannerHeight = 'height: 500px;'
      }else if (this.scroll < 1 && this.pageWidth < 700) {
        this.menuHeight = 'height: 60px; background-color: aquamarine;'
        this.bannerHeight = 'height: 640px;'
      }else if (this.scroll > 1 && this.pageWidth < 700) {
        this.menuHeight = 'height: 60px; background-color: burlywood;'
        this.bannerHeight = 'height: 640px;'
      }
    },
  },
  mounted() {
    this.handleResponsivePage()
  }
}
</script>
<style>
  .header {
    background-color: antiquewhite;
  }
  .carousel {
    color: crimson;
  }
  .menu {
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
