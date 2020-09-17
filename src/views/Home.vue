<template>
  <v-card>
    <main-sliders />
    <best-products />
    <hot-deal />
    <signature />
  </v-card>
</template>

<script>
import MainSliders from '@/components/MainSliders'
import BestProducts from '@/components/BestProducts'
import HotDeal from '@/components/HotDeal'
import Signature from '@/components/Signature'

export default {
  name: 'App',

  components: {
    MainSliders,
    BestProducts,
    HotDeal,
    Signature
  },

  data: () => ({
    //
  })
}
</script>
