<template>
  <div class="navbar-mobile" :class="{ active: active }">
    <h1>Hello world</h1>
  </div>
</template>

<script>
export default {
  name: 'navbar-mobile',
  mounted: function () {
    this.$parent.$on('toggleNav', () => {
      console.log('received2', this.active)
      this.active = !this.active
    })
  },
  data: function () {
    return {
      active: false
    }
  }
}
</script>

<style lang="scss">
  .navbar-mobile {
    display: none;
  }
  .active {
    display: block;
  }
</style>
