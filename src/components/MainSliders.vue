<template>
  <v-card>
    <v-carousel
      cycle
      height="253"
      interval="3000"
      hide-delimiter-background
      delimiter-icon="mdi-minus"
      show-arrows-on-hover
      class="mainSlider d-md-none"
    >
      <v-carousel-item
        v-for="(slide, i) in slides"
        :key="i"
        :src="slide.src_mobile"
      >
        <v-sheet
          v-if="slide.title"
          width="80%"
          height="160"
          class="mx-auto mt-15 px-5 tBder_1"
          color="rgba(0,0,0,.7)"
        >
          <v-row
            class="fill-height"
            align="center"
            justify="center"
            dense
          >
            <div class="text-h5">{{ slide.title }}</div>
            <div class="subtitle-1">{{ slide.content }}</div>
          </v-row>
        </v-sheet>
      </v-carousel-item>
    </v-carousel>
    <v-carousel
      cycle
      height="650"
      interval="3000"
      hide-delimiter-background
      :show-arrows="false"
      class="d-none d-md-flex d-sm-none"
    >
      <v-carousel-item
        v-for="(slide, i) in slides"
        :key="i"
        :src="slide.src_pc"
      >
        <!-- <v-sheet
          v-if="slide.title"
          width="80%"
          height="160"
          class="mx-auto mt-15 px-5 tBder_1"
          color="rgba(0,0,0,.7)"
        >
          <v-row
            class="fill-height"
            align="center"
            justify="center"
            dense
          >
            <div class="text-h5">{{ slide.title }}</div>
            <div class="subtitle-1">{{ slide.content }}</div>
          </v-row>
        </v-sheet> -->
      </v-carousel-item>
    </v-carousel>
  </v-card>
</template>

<script>
export default {
  data () {
    return {
      slides: [
        {
          src_pc: require('@/assets/pc_slider1.jpg'),
          src_mobile: require('@/assets/slider1.jpg')
        },
        {
          title: '태국의 숨겨진 대자연 속으로',
          content: '카오야이 국립공원과 아유타야 이색 문화 트레킹 3박5일!',
          src_pc: require('@/assets/pc_slider2.jpg'),
          src_mobile: require('@/assets/slider2.jpg')
        },
        {
          title: '규슈올레 다.아.미 3코스/온천 4일',
          content: '다케오-아마쿠사-미나미시마바라 3코스!(인천/부산 공동모객!)',
          src_pc: require('@/assets/pc_slider3.jpg'),
          src_mobile: require('@/assets/slider3.jpg')
        },
        {
          title: '러시아의 진주 바이칼 호수',
          content: '몽골에서 시베리아 횡단열차타고 바이칼호수까지♪',
          src_pc: require('@/assets/pc_slider4.jpg'),
          src_mobile: require('@/assets/slider4.jpg')
        },
        {
          title: '도란도란 부관겨울맛집 오뎅투어!',
          content: '2/27_ 139,000원 집중 모객중!!',
          src_pc: require('@/assets/pc_slider5.jpg'),
          src_mobile: require('@/assets/slider5.jpg')
        }
      ]
    }
  }
}
</script>
