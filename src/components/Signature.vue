<template>
  <v-container
    class="Signature"
  >
    <div class="text-h6 text-center font-weight-black pt-2">시그니처</div>
    <v-row
      class="pt-1"
    >
      <v-col
        class="pa-0"
      >
        <v-carousel
          cycle
          interval="3500"
          hide-delimiters
          :show-arrows="false"
          show-arrows-on-hover
          progress
          progress-color="#a0ce54"
          height="300"
        >
          <v-carousel-item
            v-for="(slide, i) in Signature"
            :key="i"
            :src="slide.src"
            gradient="to bottom, rgba(0,0,0,0), rgba(0,0,0,.2)"
          >
            <v-sheet
                v-if="slide.title"
                width="92%"
                height="95%"
                class="mx-auto"
                color="rgba(0,0,0,.0)"
            >
              <v-row
              class="fill-height cstom_bg"
              align="end"
              justify="start"
              dense
              >
                <div class="text-h6">{{ slide.title }}</div>
              </v-row>
            </v-sheet>
          </v-carousel-item>
        </v-carousel>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  data () {
    return {
      Signature: [
        {
          title: '후쿠오카 쇼핑 99패키지 3일',
          src: require('@/assets/signature1.jpg')
        },
        {
          title: '대만 예.스.폭.진.지 1일투어',
          src: require('@/assets/signature2.jpg')
        },
        {
          title: '북해도 비에이&후라노 1일투어',
          src: require('@/assets/signature3.jpg')
        },
        {
          title: '마카오 필수관광지 1일투어',
          src: require('@/assets/signature4.jpg')
        },
        {
          title: '화련 타이루거 협곡 1일투어',
          src: require('@/assets/signature5.jpg')
        },
        {
          title: '오사카 교토 1일투어',
          src: require('@/assets/signature6.jpg')
        }
      ]
    }
  }
}
</script>
