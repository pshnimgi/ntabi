<template>
  <v-container
    class="HotDeal py-0 grey lighten-3"
  >
    <div class="text-h6 text-center font-weight-black pt-2">핫딜</div>
    <v-row
      class="pt-1 d-md-none"
    >
      <v-col
        cols="12"
        class="pt-0"
      >
        <v-card
          :elevation="0"
          class="grey lighten-3"
        >
          <v-container
            fluid
            class="ma-0 pa-1"
          >
            <v-row>
              <v-col
                v-for="Product in HotDeal"
                :key="Product.title"
                class="d-flex child-flex px-1 py-4"
                cols="6"
              >
                <v-card>
                  <v-img
                    :src="Product.src"
                    aspect-ratio="1.4"
                    class="align-end"
                  >
                    <v-card-text
                      class="pa-1"
                    >
                      <v-chip
                          class="ma-1 pa-1"
                          color="green"
                          text-color="white"
                          x-small
                      >
                          {{ Product.theme }}
                      </v-chip>
                      <v-chip
                          class="ma-0 pa-1"
                          color="primary"
                          text-color="white"
                          x-small
                      >
                          {{ Product.transport }}
                      </v-chip>
                    </v-card-text>
                  </v-img>
                  <v-card-title
                    class="caption pa-1"
                  >
                      {{ Product.title }}
                  </v-card-title>
                  <v-card-subtitle
                    class="subtitle-1 pa-1 text-right"
                  >
                      {{ Product.price }}
                  </v-card-subtitle>
                </v-card>
              </v-col>
              <v-col
                v-for="Product in SpecialPrice"
                :key="Product.title"
                class="d-flex child-flex px-1 py-4"
                cols="6"
              >
                <v-card>
                  <v-img
                    :src="Product.src"
                    aspect-ratio="1.4"
                    class="oflow_init"
                  >
                    <v-img
                     src="@/assets/special_price_title.png"
                     width="70%"
                     class="mx-auto mt-n6"
                    ></v-img>
                  </v-img>
                  <v-card-title
                    class="caption pa-1"
                  >
                    {{ Product.title }}
                  </v-card-title>
                  <v-card-subtitle
                    class="subtitle-1 pa-1 text-right"
                  >
                    {{ Product.price }}
                  </v-card-subtitle>
                </v-card>
              </v-col>
            </v-row>
          </v-container>
        </v-card>
      </v-col>
    </v-row>
    <v-card
      class="d-none d-md-flex d-sm-none grey lighten-3"
      flat
      tile
    >
      <v-row
        class="pt-1"
      >
        <v-col
          cols="12"
          class="pt-0"
        >
          <v-card
            :elevation="0"
            class="grey lighten-3 mx-auto"
            max-width="1200"
          >
            <v-container
              fluid
              class="ma-0 pa-1"
            >
              <v-row>
                <v-col
                  v-for="Product in HotDeal"
                  :key="Product.title"
                  class="d-flex child-flex px-1 py-4"
                  cols="3"
                >
                  <v-card>
                    <v-img
                      :src="Product.src"
                      aspect-ratio="1.4"
                      class="align-end"
                    >
                      <v-card-text
                        class="pa-1"
                      >
                        <v-chip
                            class="ma-1 pa-1"
                            color="green"
                            text-color="white"
                            x-small
                        >
                            {{ Product.theme }}
                        </v-chip>
                        <v-chip
                            class="ma-0 pa-1"
                            color="primary"
                            text-color="white"
                            x-small
                        >
                            {{ Product.transport }}
                        </v-chip>
                      </v-card-text>
                    </v-img>
                    <v-card-title
                      class="text-h6 pa-1"
                    >
                        {{ Product.title }}
                    </v-card-title>
                    <v-card-subtitle
                      class="text-subtitle-1 pa-1 text-right"
                    >
                        {{ Product.price }}
                    </v-card-subtitle>
                  </v-card>
                </v-col>
                <v-col
                  v-for="Product in SpecialPrice"
                  :key="Product.title"
                  class="d-flex child-flex px-1 py-4"
                  cols="3"
                >
                  <v-card>
                    <v-img
                      :src="Product.src"
                      aspect-ratio="1.4"
                      class="oflow_init"
                    >
                      <v-img
                      src="@/assets/special_price_title.png"
                      width="50%"
                      class="mx-auto mt-n9"
                      ></v-img>
                    </v-img>
                    <v-card-title
                      class="text-h6 pa-1"
                    >
                      {{ Product.title }}
                    </v-card-title>
                    <v-card-subtitle
                      class="text-subtitle-1 pa-1 text-right"
                    >
                      {{ Product.price }}
                    </v-card-subtitle>
                  </v-card>
                </v-col>
              </v-row>
            </v-container>
          </v-card>
        </v-col>
      </v-row>
    </v-card>
  </v-container>
</template>

<script>
export default {
  data () {
    return {
      SpecialPrice: [
        {
          title: '카멜리아 2박3일 특가 승선권',
          price: '43,000 원',
          src: require('@/assets/SpecialPrice.jpg'),
          days: '04/13, 04/14'
        }
      ],
      HotDeal: [
        {
          title: '부관훼리 2박3일 왕복승선권',
          price: '57,000 원',
          src: require('@/assets/hotdeal1.jpg'),
          theme: '자유여행',
          transport: '부관훼리'
        },
        {
          title: '비틀(후쿠오카) 2박3일 왕복승선권',
          price: '55,000 원',
          src: require('@/assets/hotdeal2.jpg'),
          theme: '자유여행',
          transport: '비틀'
        },
        {
          title: '[승선권] 팬스타 크루즈 여행  4박5일 "일, 화" 출발',
          price: '37,000 원',
          src: require('@/assets/hotdeal3.jpg'),
          theme: '자유여행',
          transport: '팬스타'
        }
      ]
    }
  }
}
</script>
