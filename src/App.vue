<template>
  <v-app>
    <site-header></site-header>
    <v-main>
      <router-view/>
    </v-main>
    <v-divider class="py-2" />
    <site-footer></site-footer>
  </v-app>
</template>

<script>
import SiteHeader from '@/components/header'
import SiteFooter from '@/components/Footer'

export default {
  name: 'App',

  components: {
    SiteHeader,
    SiteFooter
  },

  data: () => ({
    //
  })
}
</script>
