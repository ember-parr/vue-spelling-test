<template>
  <v-app>
    <v-app-bar app color="blue-grey" dark>
      <div class="d-flex align-center">
        <p>Can You Spell It?</p>
      </div>
      <v-spacer></v-spacer>

    </v-app-bar>

    <v-main class="d-flex justify-center">
      <div v-if="index < AllWords.length">
        <SpellingTest :currentIndex="index" @spelling-saved="saveSpelling" />
      </div>
      <div v-else>
        <results />
      </div>
    </v-main>
  </v-app>
</template>

<script>
import SpellingTest from "./components/SpellingTest";
import Results from "./components/Results";
import words from "./assets/words";
export default {
  name: "App",
    data: () => ({
      AllWords: words, 
      index: 0
    }),

  components: {
    SpellingTest,
    Results
  },
  methods: {
    saveSpelling(input) {
      this.AllWords[this.index].userInput = input.spelling;
      this.index += 1;
    }
  },

};
</script>

<style scoped>
</style>