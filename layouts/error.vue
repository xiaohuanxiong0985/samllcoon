<template>
  <div class="container">
    <h1 v-if="error.statusCode === 404">
      页面不存在
    </h1>
    <h1 v-else>
      应用发生错误异常
    </h1>
    <nuxt-link to="/">
      首 页
    </nuxt-link>
  </div>
</template>

<script>
export default {
  layout: 'blog',
  // eslint-disable-next-line vue/require-prop-types
  props: ['error'] // 你可以为错误页面指定自定义的布局
}
</script>
