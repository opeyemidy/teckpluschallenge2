<template>
  <div>
    <v-row justify="center" align="center">
      <v-col cols="12">
        <v-card class="pa-7 custom-radius" flat color="#e4dbff">
          <v-card-title class="text-h3">Hi, Alyssa</v-card-title>
          <v-card-subtitle class="text-subtitle-1 black--text"
            >Ready to start your day with some pitch decks?</v-card-subtitle
          >
        </v-card>
      </v-col>
    </v-row>
    <v-row>
      <v-col cols="12" class="pb-0">
        <div class="text-subtitle-1">Overview</div>
      </v-col>
      <v-col
        v-for="(infoCard, i) in infoCards"
        :key="i"
        cols="12"
        sm="6"
        md="4"
        lg="3"
      >
        <info-card :info-card="infoCard" />
      </v-col>
    </v-row>
    <v-row justify="center" align="center">
      <v-col v-for="(contentCard, i) in contentCards" :key="i" cols="12">
        <content-card :content-card="contentCard" />
      </v-col>
    </v-row>
  </div>
</template>

<script>
import infoCard from '~/components/dashboard-first/infoCard.vue'
import ContentCard from '~/components/dashboard-first/contentCard.vue'
export default {
  components: {
    infoCard,
    ContentCard,
  },
  data() {
    return {
      infoCards: [
        {
          icon: 'mdi-plus',
          percentage: '83',
          subtext: 'Open Rate',
          color: '#f2cc5b',
        },
        {
          icon: 'mdi-plus',
          percentage: '77',
          subtext: 'Complete',
          color: '#503e9d',
        },
        {
          icon: 'mdi-plus',
          percentage: '91',
          subtext: 'Unique Views',
          color: '#eb6297',
        },
        {
          icon: 'mdi-plus',
          percentage: '126',
          subtext: 'Total Views',
          color: '#ccc1eb',
        },
      ],
      contentCards: [
        {
          title: 'Next in Fashion',
          description:
            'Sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum. Lorem ipsum dolor sit amet consectetur adipisicing elit. Beatae fugit eius magnam, commodi mollitia obcaecati quas totam laborum aperiam, ullam quibusdam reiciendis possimus fugiat odio distinctio ipsam explicabo autem cumque!',
          imageUrl:
            'https://image.freepik.com/free-photo/fashion-model-beautiful-girl-yellow-background_156359-1122.jpg',
        },
        {
          title: 'Digital Marketing Today',
          description:
            'Sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum. Lorem ipsum dolor sit amet consectetur adipisicing elit. Beatae fugit eius magnam, commodi mollitia obcaecati quas totam laborum aperiam, ullam quibusdam reiciendis possimus fugiat odio distinctio ipsam explicabo autem cumque!',
          imageUrl:
            'https://image.freepik.com/free-vector/digital-marketing-icons-collection_23-2147501682.jpg',
        },
      ],
    }
  },
}
</script>
<style scoped>
.custom-radius {
  border-radius: 20px;
}
.custom-radius-info-cards {
  border-radius: 10px;
}
</style>
