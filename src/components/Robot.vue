<template>
  <div >
      <v-col>
        <v-row >
            <p>  Word {{ word.id }} of 10</p>
        </v-row>
        <v-row>
            <img alt="Sound Icon" src="../assets/sound-icon.png" class="soundIcon" @click="readWord" />
        </v-row>
        <v-row>
            <h4 @click="readWord" class="mb-10 justify-center">Hear The Word</h4>
        </v-row>
      </v-col>
  </div>
</template> 

<script>
export default {
  props: ["word"],
  data() {},
  methods: {
      readWord() {
          const utterance = new SpeechSynthesisUtterance(this.word.word);
          speechSynthesis.speak(utterance);
      }
  },
  watch: {
    word() {
      this.readWord();
    }
  }
};
</script>

<style scoped>
.soundIcon {
  width: 15%;
  height: auto;
}
</style>
