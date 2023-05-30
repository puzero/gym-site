<template>
  <section :class="this.$vuetify.theme.dark ? '' : 'grey lighten-4'">
    <v-dialog v-model="dialogIsOpened" width="500">
      <v-card>
        <v-card-title class="headline grey lighten-2" primary-title>
          {{ dialogArticle.title }}
        </v-card-title>
        <v-img class="white--text align-end" :src="dialogArticle.picture">
        </v-img>
        <v-card-text v-html="dialogArticle.text" />

        <v-divider></v-divider>

        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn color="primary" flat @click="dialogIsOpened = false"
            >Закрыть</v-btn
          >
        </v-card-actions>
      </v-card>
    </v-dialog>
    <v-row no-gutters>
      <v-col cols="12">
        <SectionsHeroAlt :hero-alt="category" />
      </v-col>
    </v-row>
    <v-container>
      <v-row style="justify-content: center">
        <v-col cols="12" xl="10" lg="9" md="8" sm="8" class="py-16">
          <v-row>
            <v-col
              v-for="(article, index) in articles"
              :key="index"
              cols="12"
              sm="6"
              md="6"
              lg="4"
              xl="3"
            >
              <v-card max-width="450" class="mx-auto" elevation="1">
                <v-img
                  class="white--text align-end"
                  height="200px"
                  :src="article.picture"
                >
                </v-img>
                <v-card-text
                  class="title font-weight-bold mt-3 pb-0 text--primary"
                  style="line-height: 1.8rem; height: 80px"
                >
                  {{ article.title }}
                </v-card-text>
                <v-card-text class="text--primary">
                  <div
                    style="height: 120px"
                    v-html="`${article.text.substring(0, 100)}...`"
                  ></div>
                  <v-btn @click="switchOpened(article)">Подробнее</v-btn>
                </v-card-text>
              </v-card>
            </v-col>
          </v-row>
        </v-col>
      </v-row>
    </v-container>
  </section>
</template>

<script>
import articlesSrc from '~/static/articles.js'
import categoriesSrc from '~/static/categories'

export default {
  data() {
    return {
      articles: articlesSrc.filter(
        (article) =>
          article.category === this.$route.params.category &&
          article.section === this.$route.params.section
      ),
      category: categoriesSrc.filter(
        (category) => category.code === this.$route.params.category
      ),
      dialogIsOpened: false,
      dialogArticle: {},
      heroAlt: [
        {
          src: '/pictures/bud_silnee.jpg',
          heading: 'Будь сильнее!',
        },
      ],
    }
  },
  methods: {
    switchOpened(article) {
      this.dialogIsOpened = true
      this.dialogArticle = article
    },
  },
  head() {
    return {
      title: 'Blog',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content:
            'Infographic hypotheses influencer user experience Long madel ture gen-z paradigm shift client partner network product seilans solve management influencer analytics leverage virality. incubator seed round massmarket. buyer agile development growth hacking business-to-consumer ecosystem',
        },
      ],
    }
  },
}
</script>
