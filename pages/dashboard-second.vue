<template>
  <v-card class="fill-height" style="border-radius: 20px" width="100%">
    <v-container fluid class="px-5">
      <v-row class="fill-height">
        <v-col cols="12" md="8">
          <div>
            <v-card color="#f2c94c" style="border-radius: 15px" flat>
              <v-card-title
                class="text-h4 font-weight-medium"
                style="color: #232946"
              >
                Hello Sarah!</v-card-title
              >
              <v-card-text
                class="text-subtitle-2 font-weight-medium"
                style="color: #232946"
                >Lorem ipsum dolor sit amet consectetur adipisicing elit.
                Inventore dignissimos repellat iste possimus eveniet
                quaerat</v-card-text
              >
              <v-card-actions class="pl-4 pb-4">
                <v-btn
                  color="#232946"
                  class="text-lowercase"
                  dark
                  style="color: #eebbc3"
                  ><span class="text-uppercase">w</span>
                  rite new post
                </v-btn>
              </v-card-actions>
            </v-card>
          </div>
          <div class="mt-3">
            <v-card flat color="#f4f6ff" style="border-radius: 15px">
              <v-card-title class="justify-space-between"
                >Top articles
                <v-btn text small>
                  <v-icon left>mdi-calendar-range-outline</v-icon>
                  <span class="text-capitalize"
                    >january<v-icon small>mdi-chevron-down</v-icon></span
                  >
                </v-btn></v-card-title
              >
              <v-card-text class="pa-0">
                <!-- card info component -->
                <card-info
                  v-for="cardInfo in cardInfos"
                  :key="cardInfo.id"
                  :card-info="cardInfo"
                />
              </v-card-text>
            </v-card>
          </div>
        </v-col>
        <v-col cols="12" class="d-none d-md-block" md="4">
          <v-card color="#bbebee" class="mb-5" style="border-radius: 8px" flat>
            <v-card-text class="px-0 py-2">
              <v-row class="ma-0">
                <v-col cols="3" class="d-flex">
                  <div
                    style="position: relative; width: 50px"
                    class="d-flex justify-center align-center"
                  >
                    <div
                      style="
                        position: absolute;
                        height: 50px;
                        width: 50px;
                        border-radius: 12px;
                        background-color: #232946;
                      "
                    ></div>
                    <v-icon color="#eebbc3" large dark>mdi-plus</v-icon>
                  </div>
                </v-col>
                <v-col cols="9">
                  <div class="text-h4" style="color: #232946">$620</div>
                  <div class="text-subtitle-2" style="color: #586d81">
                    Total earnings
                  </div>
                </v-col>
              </v-row>
            </v-card-text>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </v-card>
</template>

<script>
import cardInfo from '~/components/dashboard-second/cardInfo.vue'
export default {
  components: { cardInfo },
  layout: 'dashboardSecond',
  data() {
    return {
      cardInfos: [
        {
          id: '01',
          content: `Disney's motion principles in designing interface animations`,
          date: 'Jan 13, 2020',
          views: 6.5,
          likes: 3.4,
          cash: 34,
        },
        {
          id: '02',
          content: `How Airbnb drives users actions with their landing page design`,
          date: 'Jan 13, 2020',
          views: 5.3,
          likes: 3.1,
          cash: 28,
        },
        {
          id: '03',
          content: `It's Time for Tech to Ask 'Should We' Instead of 'Could We'`,
          date: 'Jan 13, 2020',
          views: 3.1,
          likes: 2.2,
          cash: 25,
        },
        {
          id: '04',
          content: `Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullam fermentum et erat elementum tincidunt. Quisque ac felis vitae augue ultricies dignissim nec pretium purus. Curabitur at justo suscipit, venenatis mi eget, ultricies tellus. Sed lacinia, felis vel pretium sodales, nunc neque porttitor felis, sed porta dui quam nec augue. Sed at mi scelerisque, volutpat tellus sit amet, cursus elit.`,
          date: 'Jan 13, 2020',
          views: 3.1,
          likes: 2.2,
          cash: 25,
        },
      ],
    }
  },
}
</script>
