<template>
  <div class="mytoolbar"><vue-file-toolbar-menu :content="my_menu" /></div>
</template>
<script>
import VueFileToolbarMenu from 'vue-file-toolbar-menu'
export default {
  name: 'Toolbar',
  components: { VueFileToolbarMenu },

  data() { return { happy: false } },

  computed: {
    my_menu() {
      return [
        { text: 'My Menu', menu: [
          { text: 'Item 1', click: () => alert('Action 1') },
          { text: 'Item 2', click: () => alert('Action 2') }
        ] }, {
          text: 'My Button',
          active: this.happy,
          icon: this.happy ? 'sentiment_very_satisfied' : 'sentiment_satisfied',
          click: () => { this.happy = !this.happy }
        }
      ]
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
}
</style>
