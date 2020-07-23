<template>
  <div class="mytoolbar"><vue-file-toolbar-menu :content="my_menu" /></div>
</template>
<script>
import VueFileToolbarMenu from 'vue-file-toolbar-menu'
export default {
  name: 'Toolbar',
  components: { VueFileToolbarMenu },
  props: {
    toolbarData: {
      type: Object,
      default() {
        return {}
      }
    }
  },
  data() {
    return {
      happy: false,
      menuDatas: [],
      defaultToolbarData: {
        titleData: {
          text: '测试标题111',
          active: this.happy,
          click: () => { alert('test') }
        },
        toolDatas: [
          {
            text: '新增',
            active: this.happy,
            icon: this.happy ? 'sentiment_very_satisfied' : 'sentiment_satisfied',
            click: () => { this.happy = !this.happy }
          }, {
            text: '删除',
            active: this.happy,
            icon: this.happy ? 'sentiment_very_satisfied' : 'sentiment_satisfied',
            click: () => { this.happy = !this.happy }
          }, {
            text: '修改',
            active: this.happy,
            icon: this.happy ? 'sentiment_very_satisfied' : 'sentiment_satisfied',
            click: () => { this.happy = !this.happy }
          }, {
            text: '导出',
            active: this.happy,
            icon: this.happy ? 'sentiment_very_satisfied' : 'sentiment_satisfied',
            click: () => { this.happy = !this.happy }
          }
        ]
      }
    }
  },
  computed: {
    my_menu() {
      this.initData()
      return this.menuDatas
      // return [
      //   { text: 'My Menu', menu: [
      //     { text: 'Item 1', click: () => alert('Action 1') },
      //     { text: 'Item 2', click: () => alert('Action 2') }
      //   ] },
      //   {
      //     text: 'My Button',
      //     active: this.happy,
      //     icon: this.happy ? 'sentiment_very_satisfied' : 'sentiment_satisfied',
      //     click: () => { this.happy = !this.happy }
      //   },
      //   {
      //     text: '用户列表',
      //     active: this.happy,
      //     click: () => { alert('test') }
      //   }
      // ]
    }
  },
  methods: {
    initData: function() {
      this.toolbarData = this.toolbarData.titleData && this.toolbarData.toolDatas && this.toolbarData || this.defaultToolbarData
      this.menuDatas = []
      this.menuDatas.push(this.toolbarData['titleData'])
      this.menuDatas = this.menuDatas.concat(this.toolbarData['toolDatas'])
    }
  }
}
</script>
<style lang="scss">
.mytoolbar {
    display: flex;
    position: relative;
    width: 100%;
    line-height: 36px;
    background: #fff;
    text-align: center;
    overflow: hidden;
    border-bottom: 1px solid #dad5d5;
}
.mytoolbar .bar {
  text-align: center;
  .bar-button {
    min-width: 120px;
  }
}

</style>
