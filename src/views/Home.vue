<template>
  <v-card>
    <main-sliders />
    <v-card
      class="d-none d-md-flex d-sm-none"
      color="grey lighten-3"
    >
      <v-container
        fluid
      >
        <v-row>
          <v-col cols="12">
            <v-row
              align="center"
              justify="center"
              class="py-5"
            >
              <v-btn-toggle
                v-model="text"
                tile
                group
              >
                <v-btn
                  width="200"
                >
                  <v-card flat tile color="transparent">
                    <v-img
                      src="@/assets/pc_icon_promotion.png"
                      class="align-end"
                      width="64"
                      height="64"
                    >
                      <template v-slot:placeholder>
                        <v-row
                          class="fill-height ma-0"
                          align="center"
                          justify="center"
                        >
                          <v-progress-circular
                            indeterminate
                          />
                        </v-row>
                      </template>
                    </v-img>
                    <v-card-subtitl class="text-caption text-center font-weight-black pa-0 ma-0">
                      기획전
                    </v-card-subtitl>
                  </v-card>
                </v-btn>
                <v-btn
                  width="200"
                >
                  <v-card flat tile color="transparent">
                    <v-img
                      src="@/assets/pc_icon_wifi.png"
                      class="align-end"
                      width="64"
                      height="64"
                    >
                      <template v-slot:placeholder>
                        <v-row
                          class="fill-height ma-0"
                          align="center"
                          justify="center"
                        >
                          <v-progress-circular
                            indeterminate
                          />
                        </v-row>
                      </template>
                    </v-img>
                    <v-card-subtitl class="text-caption text-center font-weight-black pa-0 ma-0">
                      포켓 와이파이
                    </v-card-subtitl>
                  </v-card>
                </v-btn>
                <v-btn
                  width="200"
                >
                  <v-card flat tile color="transparent">
                    <v-img
                      src="@/assets/pc_icon_insurance.png"
                      class="align-end"
                      width="64"
                      height="64"
                    >
                      <template v-slot:placeholder>
                        <v-row
                          class="fill-height ma-0"
                          align="center"
                          justify="center"
                        >
                          <v-progress-circular
                            indeterminate
                          />
                        </v-row>
                      </template>
                    </v-img>
                    <v-card-subtitl class="text-caption text-center font-weight-black pa-0 ma-0">
                      여행자 보험
                    </v-card-subtitl>
                  </v-card>
                </v-btn>
                <v-btn
                  width="200"
                >
                  <v-card flat tile color="transparent">
                    <v-img
                      src="@/assets/pc_icon_pass.png"
                      class="align-end"
                      width="64"
                      height="64"
                    >
                      <template v-slot:placeholder>
                        <v-row
                          class="fill-height ma-0"
                          align="center"
                          justify="center"
                        >
                          <v-progress-circular
                            indeterminate
                          />
                        </v-row>
                      </template>
                    </v-img>
                    <v-card-subtitl class="text-caption text-center font-weight-black pa-0 ma-0">
                      패스/티켓
                    </v-card-subtitl>
                  </v-card>
                </v-btn>
                <v-btn
                  width="200"
                >
                  <v-card flat tile color="transparent">
                    <v-img
                      src="@/assets/pc_icon_rentcar.png"
                      class="align-end"
                      width="64"
                      height="64"
                    >
                      <template v-slot:placeholder>
                        <v-row
                          class="fill-height ma-0"
                          align="center"
                          justify="center"
                        >
                          <v-progress-circular
                            indeterminate
                          />
                        </v-row>
                      </template>
                    </v-img>
                    <v-card-subtitl class="text-caption text-center font-weight-black pa-0 ma-0">
                      렌트카
                    </v-card-subtitl>
                  </v-card>
                </v-btn>
                <v-btn
                  width="200"
                >
                  <v-card flat tile color="transparent">
                    <v-img
                      src="@/assets/pc_icon_booking.png"
                      class="align-end"
                      width="64"
                      height="64"
                    >
                      <template v-slot:placeholder>
                        <v-row
                          class="fill-height ma-0"
                          align="center"
                          justify="center"
                        >
                          <v-progress-circular
                            indeterminate
                          />
                        </v-row>
                      </template>
                    </v-img>
                    <v-card-subtitl class="text-caption text-center font-weight-black pa-0 ma-0">
                      부킹닷컴
                    </v-card-subtitl>
                  </v-card>
                </v-btn>
              </v-btn-toggle>
            </v-row>
          </v-col>
        </v-row>
      </v-container>
    </v-card>
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
