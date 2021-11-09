<template>
  <div class="warp">
    <h1 class="animate__animated animate__backInLeft">
      An animated element
    </h1>
  </div>
</template>

<script>
import 'animate.css'
export default {
  data () {
    return {
      title: '',
      des: ''
    }
  },
  head () {
    return {
      title: this.title,
      meta: [
        { hid: 'keywords', name: 'keywords', content: 'nuxt,小浣熊,ssr' },
        { hid: 'description', name: 'description', content: 'My custom description' }
      ]
    }
  },
  mounted () {
    this.$myInjectedFunction('test')
  }
}
</script>
<style scoped lang="scss">
.warp {
  display: flex;
  flex-direction: column;
}

</style>
