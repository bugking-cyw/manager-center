<template>
  <div>
    <div class="content-toolbar _md _md-toolbar-transitions" />
    <div class="dashboard-container">
      <div class="dashboard-text">name: {{ name }}</div>
    </div>
  </div>
</template>

<script>
import { mapGetters } from 'vuex'

export default {
  name: 'Dashboard',
  computed: {
    ...mapGetters([
      'name'
    ])
  }
}
</script>

<style lang="scss" scoped>
.content-toolbar, md-toolbar.sidebar-toolbar {
    color: rgba(0, 0, 0, 0.87);
    background-color: transparent;
    border-bottom: 1px solid #d3d3d3;
}
._md-toolbar-transitions {
    transition-duration: .5s;
    transition-timing-function: cubic-bezier(.35,0,.25,1);
    transition-property: background-color,fill,color;
}
md-toolbar {
    min-height: 54px;
    max-height: 54px;
}
body * {
    font-family: Roboto, "PingFang SC", "Helvetica Neue", sans-serif;
}
md-toolbar {
    box-sizing: border-box;
    display: flex;
    flex-direction: column;
    position: relative;
    z-index: 2;
    font-size: 20px;
    min-height: 64px;
    width: 100%;
}
.dashboard {
  &-container {
    margin: 30px;
  }
  &-text {
    font-size: 30px;
    line-height: 46px;
  }
}
</style>
