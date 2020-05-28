<template>
  <div class="wrapper" ref="wrapper">
    <slot></slot>
  </div>
</template>

<script>
import BSscroll from 'better-scroll'

export default {
  name: 'Scroll',

  props: {
    handleToScroll: {
      type: Function,
      default: function () {}
    },
    handleToTouchEnd: {
      type: Function,
      default: function () {}
    }
  },

  mounted () {
    // eslint-disable-next-line no-new
    var scroll = new BSscroll(this.$refs.wrapper, {
      tap: true,
      probeType: 1
    })

    this.scroll = scroll

    scroll.on('scroll', (pos) => {
      this.handleToScroll(pos)
    })

    scroll.on('touchEnd', (pos) => {
      this.handleToTouchEnd(pos)
    })
  },

  methods: {
    toScrollTop (y) {
      this.scroll.scrollTo(0, y)
    }
  }
}
</script>

<style>
.wrapper{
  height: 100%;

}
</style>
