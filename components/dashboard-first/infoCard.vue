<template>
  <v-card flat :color="infoCard.color" class="custom-radius-info-cards" dark>
    <v-card-text class="d-flex align-center">
      <v-container>
        <v-row align="center">
          <v-col cols="3">
            <div
              style="position: relative"
              class="d-flex justify-center align-center"
            >
              <div
                style="
                  position: absolute;
                  height: 50px;
                  width: 50px;
                  opacity: 0.3;
                  border-radius: 5px;
                "
                class="white"
              ></div>
              <v-icon large>{{ infoCard.icon }}</v-icon>
            </div>
          </v-col>
          <v-col cols="9"
            ><div class="text-h5 font-weight-bold white--text">
              {{ infoCard.percentage
              }}{{ infoCard.subtext !== 'Total Views' ? '%' : '' }}
            </div>
            <div class="white--text">{{ infoCard.subtext }}</div></v-col
          >
        </v-row>
      </v-container>
    </v-card-text>
  </v-card>
</template>

<script>
export default {
  props: {
    infoCard: {
      type: Object,
      default: () => {
        return {}
      },
    },
  },
}
</script>

<style lang="scss" scoped></style>
