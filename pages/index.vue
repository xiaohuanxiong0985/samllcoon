<template>
  <div class="warp">
    <h1>{{ title }}</h1>
    <h2>{{ des }}</h2>
  </div>
</template>

<script>
export default {
  data () {
    return {
      title: 'Hello World!',
      des: '欢迎使用nuxt'
    }
  },
  head () {
    return {
      title: this.title,
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'My custom description'
        }
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
  h1 {
    color: red;
  }
  h2 {
    color: aqua;
  }
}

</style>
