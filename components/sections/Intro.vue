<template>
  <section id="intro" class="py-16">
    <v-container>
      <v-responsive class="max-auto mx-auto text-center" max-width="600">
        <v-avatar color="primary" size="300px" class="mb-8">
          <img :src="`${$config.prefix}/pictures/ya.jpg`" />
        </v-avatar>
        <h2 class="text-h4 text-md-h3 text-center font-weight-black mb-7">
          О себе
        </h2>
        <p class="title font-weight-light">
          Привет! Меня зовут Максим. Я учусь в РЭУ им. Г.В.Плеханова по
          специальности информационные системы и программирование. Я люблю
          программировать. Также мне очень нравится ходить в тренажерный зал,
          таскать железяки и становиться сильнее. Этот сайт является результатом
          этих двух увлечений. Здесь я собрал актуальную информацию о том, как
          преобразить тело в лучшую сторону. Очень надеюсь, что каждый кто
          пришел сюда найдет то, что искал!
        </p></v-responsive
      >
      <v-row class="pt-12">
        <v-col v-for="card in cards" :key="card.title" cols="12" md="4">
          <v-row no-gutters>
            <v-col :cols="card.callout ? 9 : 12">
              <div class="pr-2">
                <div class="text--disabled" v-text="card.subtitle"></div>
                <h4
                  class="text-uppercase mt-1 mb-4"
                  style="letter-spacing: 0.15em"
                  v-text="card.title"
                ></h4>
                <p v-text="card.text"></p>
              </div>
            </v-col>
            <v-col v-if="card.callout" cols="2">
              <span
                class="text-h3 grey--text font-weight-bold pr-8"
                style="opacity: 0.1"
                >{{ card.callout }}</span
              >
            </v-col>
          </v-row>
        </v-col>
      </v-row>
    </v-container>
  </section>
</template>

<script>
export default {}
</script>
