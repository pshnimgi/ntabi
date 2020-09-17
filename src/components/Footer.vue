<template>
  <v-footer
    color="grey darken-1"
    padless
  >
    <v-row
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
