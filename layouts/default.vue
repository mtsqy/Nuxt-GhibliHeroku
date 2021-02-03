<template>
  <div class="body">
    <app-header class="body__nav"/>
    <Nuxt class="body__content" />
  </div>
</template>
<script>
import Navigation from '@/components/Navigation'

export default {
  components: {
    appHeader: Navigation
  }
}
</script>
<style lang="sass">
html 
  font-family: 'Source Sans Pro',-apple-system,BlinkMacSystemFont,'Segoe UI',Roboto,'Helvetica Neue',Arial,sans-serif
  font-size: 16px
  word-spacing: 1px
  -ms-text-size-adjust: 100%
  -webkit-text-size-adjust: 100%
  -moz-osx-font-smoothing: grayscale
  -webkit-font-smoothing: antialiased
  box-sizing: border-box
h1 
  margin: .5rem .3rem
  color: #c4c4c4
h2 
  margin: .4rem 0
h5 
  font-weight: 550
  color: #473535
p 
  font-size: .7rem
  color: #a5a5a5
ul
  margin: 0
li 
  list-style: none
a
  text-decoration: none
.body 
  display: flex
*,
*::before,
*::after 
  box-sizing: border-box
  margin: 0
::-webkit-scrollbar 
    display: none
</style>
