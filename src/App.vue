<template>
  <v-app>
    <site-header></site-header>
    <v-main>
      <HelloWorld/>
    </v-main>
  </v-app>
</template>

<script>
import HelloWorld from './components/HelloWorld'
import SiteHeader from '@/components/header'

export default {
  name: 'App',

  components: {
    HelloWorld,
    SiteHeader
  },

  data: () => ({
    //
  })
}
</script>
