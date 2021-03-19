<template>
  <div class="d-flex justify-center">
    <v-col :lg="8">
        <robot :word="currentWord" />

        <v-form @submit.prevent="handleSubmit" ref="spellingInput">
          <v-row>
            <v-text-field outlined label="Spell The Word" v-model="form.spelling" />
          </v-row>
          <v-row>
            <v-btn type="submit" color="blue-grey lighten-3" dark>Submit</v-btn>
          </v-row>
        </v-form>
        <results />
    </v-col>
  </div>
</template>

<script>
import Robot from "./Robot";
import words from "../assets/words";
export default {
  props: ["currentIndex"],
  data() {
    return {
      AllWords: words,
      form: {
        spelling: "",
      },
    };
  },
  components: {
    Robot
  },
  methods: {
    handleSubmit() {
      this.$emit("spelling-saved", this.form)
      this.form = {
        spelling: ""
      }
    },
  },
  computed: {
    currentWord() {
      return words[this.currentIndex]
    }
  }
};
</script> 

<style scoped>
</style>
