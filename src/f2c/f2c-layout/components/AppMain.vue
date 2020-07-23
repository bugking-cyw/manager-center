<template>
  <section class="app-main">
    <toolbar :toolbar-data="toolbarData" />
    <transition name="fade-transform" mode="out-in">
      <router-view :key="key" />
    </transition>
  </section>
</template>

<script>
import Toolbar from './Toolbar'
export default {
  name: 'AppMain',
  components: {
    Toolbar
  },
  data() {
    return {
      toolbarData: {
        titleData: {
          text: '测试标题222',
          click: () => { alert('test') }
        },
        toolDatas: [
          {
            text: '新增',
            icon: 'sentiment_very_satisfied',
            click: () => { alert('main组建中传递标题参数') }
          }
        ]
      }
    }
  },
  computed: {
    key() {
      return this.$route.path
    }
  }
}
</script>

<style scoped>
.app-main {
  /*50 = navbar  */
  min-height: calc(100vh - 50px);
  width: calc(100% - 210px);
  position: relative;
  overflow: auto;
  left: 210px;
  top: 50px;
}
.fixed-header+.app-main {
  padding-top: 50px;
}
</style>

<style lang="scss">
// fix css style bug in open el-dialog
.el-popup-parent--hidden {
  .fixed-header {
    padding-right: 15px;
  }
}
</style>
