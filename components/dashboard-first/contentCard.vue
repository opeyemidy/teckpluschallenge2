<template>
  <v-card
    width="100%"
    outlined
    style="border: 1px solid rgb(234 229 229 / 87%); border-radius: 10px"
    color="#f8f8f8"
  >
    <v-row class="mx-0">
      <v-col
        class="pa-5 d-flex justify-center justify-sm-start"
        cols="12"
        sm="2"
      >
        <v-card width="150" height="150" flat>
          <v-img
            :src="contentCard.imageUrl"
            :lazy-src="contentCard.imageUrl"
            aspect-ratio="1"
            class="grey lighten-2"
          ></v-img>
        </v-card>
      </v-col>
      <v-col cols="12" sm="8" class="px-5 px-sm-0">
        <p class="mt-2 font-weight-bold" style="color: #5073e8">
          {{ contentCard.title }}
        </p>
        <p>
          {{ contentCard.description }}
        </p>
      </v-col>
      <v-col cols="12" class="d-flex flex-column" sm="2">
        <div class="mt-2 d-flex justify-space-between align-center">
          <span class="font-weight-bold">Public</span>
          <v-switch
            v-model="theSwitch"
            class="ma-0"
            color="indigo darken-3"
            value="indigo darken-3"
            hide-details
          ></v-switch>
        </div>
        <v-spacer></v-spacer>
        <div class="d-flex justify-center">
          <v-spacer class="d-none d-sm-block"></v-spacer>
          <v-icon class="mr-2"> mdi-pencil-outline </v-icon>
          <v-icon> mdi-delete-outline </v-icon>
        </div>
      </v-col>
    </v-row>
  </v-card>
</template>

<script>
export default {
  props: {
    contentCard: {
      type: Object,
      default: () => {
        return {}
      },
    },
  },
  data() {
    return {
      theSwitch: 'indigo darken-3',
    }
  },
}
</script>

<style lang="scss" scoped></style>
