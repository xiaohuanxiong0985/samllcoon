<template>
  <div class="warp">
    <header :class="navShow ? 'navOn' : 'navOff'">
      表头
    </header>
    <div class="body">
      内容
    </div>
  </div>
</template>

<script>
export default {
  name: 'HomeIndex',
  data () {
    return {
      title: '测试滚动头部',
      des: '内容爱仕达卡',
      navShow: false,
      top: 0
    }
  },
  head () {
    return {
      title: this.title,
      meta: [
        { hid: 'keywords', name: 'keywords', content: 'nuxt,小浣熊,ssr' },
        { hid: 'description', name: 'description', content: '网页描述' }
      ]
    }
  },
  watch: {
    top (newVal, old) {
      if (newVal > 100) {
        if (newVal > old) {
          this.navShow = false
          console.log('向上滚动')
        } else {
          this.navShow = true
          console.log('向下滚动')
        }
      }
    }
  },
  mounted () {
    window.addEventListener('scroll', () => {
      this.top = document.documentElement.scrollTop || document.body.scrollTop || window.pageYOffset
    })
  }
}
</script>

<style scoped lang="scss">
.warp {
  header {
    height: 60px;
    background-color: rgba(255, 255, 255, .5);
    backdrop-filter: saturate(180%) blur(20px);
    position: fixed;
    top: 0;
    &.navOn {
      position: fixed;
      top: 0;
      left: 0;
      right: 0;
      transition: all .2s ease-in-out .2s;
      transform: translateZ(0);
    }
    &.navOff {
      position: fixed;
      top: 0;
      left: 0;
      right: 0;
      transition: all .2s ease-in-out .2s;
      transform: translate3d(0, -100%, 0);
    }
  }
  .body {
    height: 3000px;
    background-color: #48dbfb;
    margin-top: 60px;
  }
}
</style>
