<template>
  <div class="nav">
      <app-logo class="nav__brand"/>
      <ul class="nav__links">
          <!-- <li><nuxt-link class="nav__link" to="/">Films</nuxt-link></li>
          <li><nuxt-link class="nav__link" to="/">People</nuxt-link></li>
          <li><nuxt-link class="nav__link" to="/">Vehicles</nuxt-link></li> -->
      </ul>
  </div>
</template>

<script>
import Logo from '@/components/Logo'

export default {
    name: 'Navigation',
    components: {
        appLogo: Logo
  }
}
</script>

<style lang="sass">
.nav
    position: relative
    box-sizing: border-box
    height: 100%
    width: 240px
    &__links
        margin: 0
        position: relative
        display: block
        width: 100%
        height: 100%
    &__link
        position: relative
        display: inline-block
        color: #a5a5a5
        width: 100%
        height: 28px
</style>