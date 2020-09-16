<template>
  <v-app>
    <site-header></site-header>
    <v-main>
      <router-view/>
    </v-main>
  </v-app>
</template>

<script>
import SiteHeader from '@/components/header'

export default {
  name: 'App',

  components: {
    SiteHeader
  },

  data: () => ({
    //
  })
}
</script>
