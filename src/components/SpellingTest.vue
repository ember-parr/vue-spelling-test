<template>
    <div>
        <div v-for="singleWord in AllWords" :key="singleWord.id">
            <div v-if="singleWord.id === currentIndex">
                <robot :word="singleWord" />
            </div>
        </div>
      
      <v-form @submit.prevent="handleSave" ref="spellingInput">
        <v-text-field
          outlined
          label="Spell The Word"
          v-model="form.spelling"
        />
        <v-btn type="submit" color="blue-grey lighten-3" dark>Submit</v-btn>
       </v-form>
    </div>
</template>

<script> 
 import Robot from "./Robot";
 import words from "../assets/words";
 export default {
     data() {
        return {
             AllWords: words,
             form: {
                 spelling: ""
             },
             currentIndex: 6
         }
     },
     components: {
         Robot
     },
    methods: {
      handleSave() {
        this.$emit("word-spelled", this.form)
      }
    },
    computed: {
        CurrentWord() {
            return this.AllWords.filter(w => w.id = 1)
        }
    }
 }
</script>

<style scoped>

</style>