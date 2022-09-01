<template>
  <v-footer
    color="grey darken-1"
    padless
  >
    <v-row
      class="d-md-none"
      justify="center"
      no-gutters
    >
      <v-btn
        v-for="link in links"
        :key="link"
        color="white"
        text
        rounded
        class="pa-0 mx-6"
      >
        {{ link }}
      </v-btn>
      <v-col
        class="white py-4 text-center"
        cols="12"
      >
         <strong>1670-4601</strong>
         <!-- {{ new Date().getFullYear() }} -->
         <div>
           <v-btn
            small
            text
            class="px-1"
           >
            개인정보처리방침
           </v-btn>
           <v-divider vertical />
           <v-btn
            small
            text
            class="px-1"
          >
             여행약관
           </v-btn>
           <v-divider vertical />
           <v-btn
            small
            text
            class="px-1"
          >
             인허가보증보험
           </v-btn>
         </div>
         <div>
           <blockquote>
             엔타비 글로벌(주) | 대표 : 김윤중<br />
             사업자등록번호 : 602-81-43288<br />
             통신판매등록번호 : 제2007-부산 중구-0653<br />
             관광사업등록증 : 부산광역시 중구청 제2007-000014호<br />
           </blockquote>
         </div>
         <div>
           copyright {{ new Date().getFullYear() }}
         </div>
      </v-col>
    </v-row>
    <v-card
      class="d-none d-md-flex d-sm-none"
      tile
      flat
      width="100%"
    >
      <v-card
        class="mx-auto"
        max-width="1200"
        tile
        flat
      >
        <v-row
          justify="center"
          no-gutters
        >
          <v-col
            class="text-center pb-3"
            cols="12"
          >
            <v-btn
              text
              class="px-1"
            >
              회사소개
            </v-btn>
            <v-divider vertical inset />
            <v-btn
              text
              class="px-1"
            >
              찾아오시는길
            </v-btn>
            <v-divider vertical inset />
            <v-btn
              text
              class="px-1"
            >
              개인정보처리방침
            </v-btn>
            <v-divider vertical inset />
            <v-btn
              text
              class="px-1"
            >
              여행약관
            </v-btn>
            <v-divider vertical inset />
            <v-btn
              text
              class="px-1"
            >
              여행자보험
            </v-btn>
            <v-divider vertical inset />
            <v-btn
              text
              class="px-1"
            >
              인허가보증보험
            </v-btn>
          </v-col>
          <v-col cols="4">
            <div>
              <blockquote class="text-body-2">
                tel : 051-466-4602 / fax : 051-466-4605<br />
                email: kwonsix@ntabi.co.kr
                부산광역시 중구 중앙대로 169 504호(태영 노블리안)<br />
                평 일 : 10:00 ~ 17:00 (12:00 ~ 13:00 점심시간)<br />
                토/일요일 및 공휴일 휴무<br />
              </blockquote>
            </div>
          </v-col>
          <v-col cols="4">
            <div>
              <blockquote class="text-body-2">
                엔타비 글로벌(주) | 대표 : 김윤중<br />
                사업자등록번호 : 602-81-43288<br />
                통신판매등록번호 : 제2007-부산 중구-0653<br />
                관광사업등록증 : 부산광역시 중구청 제2007-000014호<br />
              </blockquote>
            </div>
            <div class="text-body-1">
              copyright {{ new Date().getFullYear() }} Ntabi right reserved.
            </div>
          </v-col>
          <v-col
            cols="4"
            class="text-body-2 text-right"
          >
            <div>
              <blockquote>
                예금주 : (주)엔타비글로벌<br />
                우리은행 : 1006-901-267484<br />
                국민은행 : 947801-01-285353<br />
                부산은행 : 101-2062-7230-01<br />
              </blockquote>
            </div>
          </v-col>
        </v-row>
      </v-card>
    </v-card>
  </v-footer>
</template>

<script>
export default {
  data: () => ({
    links: [
      '회사소개',
      '오시는 길'
    ]
  })
}
</script>
