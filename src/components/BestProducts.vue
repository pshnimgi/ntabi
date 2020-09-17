<template>
  <v-container
    class="BestProducts"
  >
    <div class="text-h6 text-center font-weight-black pt-2">인기 여행</div>
    <v-row
      class="pt-1"
    >
      <v-col
        class="pa-0"
      >
        <v-carousel
            cycle
            height="107"
            interval="4500"
            hide-delimiter-background
            show-arrows-on-hover
            class="bestSlider"
        >
          <v-carousel-item
          v-for="(slide, i) in BestProductsSlides"
          :key="i"
          :src="slide.src"
          >
            <v-sheet
                v-if="slide.title"
                width="92%"
                height="100"
                class="mx-auto"
                color="rgba(0,0,0,.0)"
            >
                <v-row
                class="fill-height"
                align="end"
                justify="start"
                dense
                >
                <div class="caption mt-12">{{ slide.content }}</div>
                <div class="text-h6">{{ slide.title }}</div>
                </v-row>
            </v-sheet>
          </v-carousel-item>
        </v-carousel>
      </v-col>
      <v-col
        cols="12"
        class="py-0"
      >
        <v-card
          :elevation="0"
        >
          <v-container
            fluid
            class="ma-0 pa-1"
          >
            <v-row>
              <v-col
                v-for="BestProduct in BestProducts"
                :key="BestProduct.title"
                class="d-flex child-flex pa-1"
                cols="6"
              >
                <v-card flat tile class="d-flex rounded-xl">
                  <v-img
                    :src="BestProduct.src"
                    aspect-ratio="1"
                    class="white--text align-end"
                    gradient="to bottom, rgba(0,0,0,0), rgba(0,0,0,.7)"
                  >
                    <v-card-title
                      class="pa-1"
                    >
                      <div class="caption">{{ BestProduct.title }}</div>
                      <div class="subtitle-1">{{ BestProduct.price }}</div>
                    </v-card-title>
                  </v-img>
                </v-card>
              </v-col>
            </v-row>
          </v-container>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  data () {
    return {
      BestProductsSlides: [
        {
          title: '테를지+호스타이 4박5일',
          content: '부산출발! 몽골의 겨울을 핫하게!',
          src: require('@/assets/bestproductslider3.jpg')
        },
        {
          title: '러시아의 진주 바이칼 5일',
          content: '몽골→시베리아 횡단열차',
          src: require('@/assets/bestproductslider1.jpg')
        },
        {
          title: '테를지 국립공원/유목민 체험투어',
          content: '몽골 현지투어 인기 NO1.',
          src: require('@/assets/bestproductslider2.jpg')
        }
      ],
      BestProducts: [
        {
          title: '규슈올레 다.아.미.코스 4일',
          price: '1,060,000 원',
          src: require('@/assets/bestproduct1.jpg')
        },
        {
          title: '시드니/골드코스트6일',
          price: '1,622,400 원',
          src: require('@/assets/bestproduct2.jpg')
        },
        {
          title: '부산직항 북유럽 패키지 12일',
          price: '5,990,000 원',
          src: require('@/assets/bestproduct3.jpg')
        },
        {
          title: '대만 여행의 기본! 패키지 4일',
          price: '465,400 원',
          src: require('@/assets/bestproduct4.jpg')
        }
      ]
    }
  }
}
</script>
