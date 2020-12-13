<template>
  <v-card :color="sideCard.color" class="mb-5" style="border-radius: 8px" flat>
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
            <v-icon color="#eebbc3" large dark>{{ sideCard.icon }}</v-icon>
          </div>
        </v-col>
        <v-col cols="9">
          <div class="text-h4" style="color: #232946">
            {{ sideCard.text === 'Total earnings' ? '$' : ''
            }}{{ sideCard.value }}
          </div>
          <div class="text-subtitle-2" style="color: #586d81">
            {{ sideCard.text }}
          </div>
        </v-col>
      </v-row>
    </v-card-text>
  </v-card>
</template>

<script>
export default {
  props: {
    sideCard: {
      type: Object,
      default: () => {
        return {}
      },
    },
  },
}
</script>
