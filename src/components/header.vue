<template>
  <v-card
    flat
    tile
  >
    <v-app-bar
      class="d-none d-md-flex d-sm-none pa-0 justify-center"
      height="extended"
      color="white"
      dense
      fixed
    >
      <v-row>
        <v-col
          cols="2"
        >
          <v-toolbar-title>
            <router-link
              tag="div"
              :to="{ path: '/' }"
            >
              <v-img
                src="@/assets/logo.png"
                alt="logo"
                class="mx-auto mt-1"
                :max-height="50"
                :max-width="136"
              />
              <p class="text-subtitle-1 text-center font-weight-black pa-0 ma-0">
                여행갈땐 엔타비
              </p>
            </router-link>
          </v-toolbar-title>
        </v-col>
        <v-col
          cols="10"
          class="pa-0"
        >
          <v-app-bar-nav-icon
            @click="drawer = !drawer"
            class="d-md-none"
          />
          <v-card
            class="d-none d-md-flex d-sm-none"
            flat
            tile
          >
            <v-row
              flat
              tile
            >
              <v-col
                class="d-flex justify-end pa-0"
                cols="12"
                tile
              >
                <v-btn-toggle
                  v-model="text"
                  tile
                  group
                  dense
                >
                  <v-btn>
                    <v-img
                      src="@/assets/ndtLogo.png"
                    />
                  </v-btn>
                  <v-divider vertical inset/>
                  <v-btn>
                    <div class="text-caption">
                      로그인
                    </div>
                  </v-btn>
                  <v-divider vertical inset/>
                  <v-btn>
                    <div class="text-caption">
                      회원가입
                    </div>
                  </v-btn>
                  <v-divider vertical inset/>
                  <v-btn>
                    <div class="text-caption">
                      고객센터
                    </div>
                  </v-btn>
                </v-btn-toggle>
              </v-col>
              <v-col
                class="d-flex justify-end pa-0"
                cols="12"
              >
                <v-btn-toggle
                  v-for="(item, index) in nav_menu"
                  :key="index"
                  v-model="text"
                  tile
                  group
                >
                  <v-divider
                    v-if="item.divider"
                    :key="index"
                    :inset="item.inset"
                  />
                  <v-menu
                    v-else-if="item.items"
                    open-on-hover
                    bottom
                    offset-y
                  >
                    <template
                      v-slot:activator="{ on, attrs }"
                    >
                      <v-btn
                        v-bind="attrs"
                        v-on="on"
                        :value="item.title"
                      >
                        <div class="font-weight-black text-h6">
                          {{ item.title }}
                        </div>
                      </v-btn>
                    </template>
                    <v-list>
                      <v-list-item
                        v-for="(subItem, i) in item.items"
                        :key="i"
                        :href="item.to"
                      >
                        <v-list-item-title>{{ subItem.title }}</v-list-item-title>
                      </v-list-item>
                    </v-list>
                  </v-menu>
                  <v-btn
                    v-else
                  >
                    <div class="font-weight-bold text-h6">
                          {{ item.title }}
                    </div>
                  </v-btn>
                </v-btn-toggle>
              </v-col>
            </v-row>
          </v-card>
        </v-col>
      </v-row>
    </v-app-bar>
    <v-toolbar
      class="d-md-none pa-0"
      dense
    >
      <v-row>
        <v-col cols="2" />
        <v-col>
          <v-toolbar-title>
            <router-link
              tag="div"
              :to="{ path: '/' }"
            >
              <v-img
                src="@/assets/logo.png"
                alt="logo"
                class="mx-auto mt-1"
                :max-height="28"
                :max-width="80"
              />
              <p class="text-caption text-center font-weight-black pa-0 ma-0">
                여행갈땐 엔타비
              </p>
            </router-link>
          </v-toolbar-title>
        </v-col>
        <v-col
          cols="2"
          md="9"
        >
          <v-app-bar-nav-icon
            @click="drawer = !drawer"
          />
        </v-col>
      </v-row>
    </v-toolbar>
    <v-navigation-drawer
      v-model="drawer"
      class="d-md-none"
      fixed
      app
      right
      width="80%"
      xs12
    >
      <v-toolbar flat dense>
        <v-icon @click="drawer = !drawer">
          mdi-chevron-right
        </v-icon>
        <v-btn text small>
          로그인
        </v-btn>
        <v-btn text small>
          회원가입
        </v-btn>
        <v-btn text small>
          고객센터
        </v-btn>
      </v-toolbar>
      <v-divider></v-divider>
      <v-list
        v-for="(item, index) in nav_menu"
        :key="item.title"
        class="pa-0"
      >
        <v-divider
          v-if="item.divider"
          :key="index"
          :inset="item.inset"
        />
        <v-list-group
          v-else-if="item.items"
          no-action
        >
          <template v-slot:activator>
            <v-list-item-title v-text="item.title"></v-list-item-title>
          </template>
          <v-list-item
            v-for="(subItem, i) in item.items"
            :key="i"
            :href="item.to"
          >
            <v-list-item-title v-text="subItem.title"></v-list-item-title>
          </v-list-item>
        </v-list-group>
        <v-list-item
          v-else
          :key="item.title"
          :href="item.to"
        >
          <v-list-item-title v-html="item.title"></v-list-item-title>
        </v-list-item>
      </v-list>
      <v-container fluid>
        <v-row>
          <v-col
            v-for="icon in nav_icon_menu"
            :key="icon.title"
            class="d-flex child-flex"
            cols="4"
          >
            <v-card flat tile class="d-flex">
              <v-img
                :src="icon.src"
                aspect-ratio="1"
                class="lighten-2 mx-auto"
                :alt="icon.title"
                width="42"
                height="62"
                max-width="42"
                max-height="62"
              >
                <template v-slot:placeholder>
                  <v-row
                    class="fill-height ma-0"
                    align="center"
                    justify="center"
                  >
                    <v-progress-circular
                      indeterminate
                      color="grey lighten-5"
                    />
                  </v-row>
                </template>
                <p class="text-caption text-center font-weight-black pa-0 ma-0 pt-11">
                  {{ icon.ko }}
                </p>
              </v-img>
            </v-card>
          </v-col>
        </v-row>
      </v-container>
      <v-img src="@/assets/banner_ndt_m_3.jpg" aspect-ratio="2" height="75"></v-img>
      <v-card-text>
        <strong>contact</strong>
        <div>
          <blockquote>
            tel : 1670-4601 | fax : 051-466-4605<br />
            부산광역시 중구 중앙대로 119<br />
            (상현빌딩 5층)<br />
            1호선 중앙역 17번 출구 5분거리<br />
            평일 : 10:00 ~ 17:00<br />
            (11:50 ~ 13:00 점심시간)<br />
            토/일요일 및 공휴일 휴무
          </blockquote>
        </div>
        <div>
          copyright {{ new Date().getFullYear() }}
        </div>
      </v-card-text>
    </v-navigation-drawer>
  </v-card>
</template>

<script>
export default {
  data () {
    return {
      drawer: false,
      nav_top: [
        {
          title: '로그인',
          to: '/'
        },
        {
          title: '회원가입',
          to: 'www.naver.com'
        },
        {
          title: '고객센터',
          to: 'www.nate.com'
        }
      ],
      nav_icon_menu: [
        {
          title: 'promotion',
          ko: '기획전',
          src: require('@/assets/icon_promotion.png')
        },
        {
          title: 'pass',
          ko: '패스/티켓',
          src: require('@/assets/icon_pass.png')
        },
        {
          title: 'wifi',
          ko: '포켓와이파이',
          src: require('@/assets/icon_wifi.png')
        },
        {
          title: 'rentcar',
          ko: '렌트카',
          src: require('@/assets/icon_rentcar.png')
        },
        {
          title: 'insurance',
          ko: '여행자보험',
          src: require('@/assets/icon_side_insurance.png')
        },
        {
          title: 'booking',
          ko: '부킹닷컴',
          src: require('@/assets/icon_side_booking.png')
        }
      ],
      nav_menu: [
        {
          title: '대만',
          to: '/'
        },
        {
          divider: true,
          inset: false
        },
        {
          title: '마카오',
          to: '/'
        },
        {
          divider: true,
          inset: false
        },
        {
          title: '동남아',
          to: '',
          items: [
            {
              title: '태국',
              to: '/'
            },
            {
              title: '필리핀',
              to: '/'
            },
            {
              title: '베트남',
              to: '/'
            },
            {
              title: '라오스',
              to: '/'
            }
          ]
        },
        {
          divider: true,
          inset: false
        },
        {
          title: '러시아',
          to: '',
          items: [
            {
              title: '블라디보스톡',
              to: '/'
            },
            {
              title: '캄차카',
              to: '/'
            }
          ]
        },
        {
          divider: true,
          inset: false
        },
        {
          title: '몽골',
          to: '/'
        },
        {
          divider: true,
          inset: false
        },
        {
          title: '중국',
          to: '',
          items: [
            {
              title: '상하이',
              to: '/'
            },
            {
              title: '베이징',
              to: '/'
            },
            {
              title: '칭다오',
              to: '/'
            },
            {
              title: '백두산',
              to: '/'
            },
            {
              title: '장가계',
              to: '/'
            },
            {
              title: '하이난/샤먼',
              to: '/'
            }
          ]
        },
        {
          divider: true,
          inset: false
        },
        {
          title: '일본',
          to: '',
          items: [
            {
              title: '북해도',
              to: '/'
            },
            {
              title: '오사카',
              to: '/'
            },
            {
              title: '나고야',
              to: '/'
            },
            {
              title: '오키나와',
              to: '/'
            },
            {
              title: '후쿠오카',
              to: '/'
            },
            {
              title: '동경',
              to: '/'
            },
            {
              title: '대마도',
              to: '/'
            }
          ]
        },
        {
          divider: true,
          inset: false
        },
        {
          title: '국내여행',
          to: '/'
        },
        {
          divider: true,
          inset: false
        }
      ]
    }
  }
}
</script>
