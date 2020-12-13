<template>
  <v-row class="ma-0">
    <v-col cols="12" md="8" class="d-flex align-start">
      <v-row class="ma-0" no-gutters>
        <v-col cols="12" md="4" class="d-flex">
          <span class="text-h6 mr-3">{{ cardInfo.id }}</span>
          <div>
            <v-card
              width="100"
              height="70"
              style="border-radius: 10px"
              color="blue darken-3"
            ></v-card>
          </div>
        </v-col>
        <v-col cols="12" md="8" class="pl-0 mt-3 mt-md-0">
          <div>
            <div
              style="
                height: 44px;
                display: -webkit-box;
                -webkit-line-clamp: 2;
                -webkit-box-orient: vertical;
                overflow: hidden;
                text-overflow: ellipsis;
              "
            >
              {{ cardInfo.content }}
            </div>
            <div class="font-weight-light mt-3">{{ cardInfo.date }}</div>
          </div>
        </v-col>
      </v-row>
    </v-col>
    <v-col cols="12" md="4" class="d-flex">
      <v-btn x-small text
        ><v-icon left>mdi-eye-outline</v-icon
        ><span class="text-subtitle-2">{{ cardInfo.views }}k</span></v-btn
      >
      <v-btn x-small text
        ><v-icon left>mdi-thumb-up-outline</v-icon
        ><span class="text-subtitle-2">{{ cardInfo.likes }}k</span></v-btn
      >
      <v-btn x-small text
        ><v-icon left>mdi-cash-usd-outline</v-icon
        ><span class="text-subtitle-2">{{ cardInfo.cash }}</span></v-btn
      >
    </v-col>
  </v-row>
</template>

<script>
export default {
  props: {
    cardInfo: {
      type: Object,
      default: () => {
        return {}
      },
    },
  },
}
</script>
