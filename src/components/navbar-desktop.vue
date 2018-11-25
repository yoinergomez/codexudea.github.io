<template>
  <nav class="navbar-desktop">
    <ul class="navbar-desktop_list">
      <li class="menu-button" @click="toggleNav()">
        <i class="fa fa-bars" aria-hidden="true"/>
      </li>
      <li class="navbar-desktop-brand">
        <img src="../assets/images/logo.svg" alt="codex logo">
      </li>
    </ul>
    <ul class="navbar-desktop_list">
      <li class="navbar-desktop-item">
        <a href="#events">Eventos</a>
      </li>
      <li class="navbar-desktop-item">
        <a href="#heroes">Heroes</a>
      </li>
      <li class="navbar-desktop-item">
        <a href="#hall-of-fame">Salón de la Fama</a>
      </li>
      <li class="navbar-desktop-item">
        <a href="#team">Equipo</a>
      </li>
      <li class="navbar-desktop-item">
        <a href="#speaker">Dar una charla</a>
      </li>
      <li class="navbar-desktop-item">
        <a href="#sponsors">Patrocinadores</a>
      </li>
    </ul>
  </nav>
</template>

<script>
export default {
  name: 'navbar-desktop',
  methods: {
    toggleNav: function () {
      this.$parent.$emit('toggleNav')
    }
  }
}
</script>

<style lang="scss">
@import '../styles/mixins';
@import '../styles/vars';
@import '../styles/functions';

.navbar-desktop{
  display: none;
}

@include from('small'){
  .navbar-desktop{
    display: block;

    &-nav {
      width: 100%;
      padding: 20px;
      background-color: color('astronaut');

      &-list {
        display: flex;
        align-items: center;
        justify-content: center;
      }

      &-brand {
        margin-right: 50px;
        max-width: 100px;
      }

      &-item {
        padding: 10px;
      }

      a {
        text-decoration: none;
        color: color(white);
        font-size: font('font-16');
      }
    }
  }
}
</style>
