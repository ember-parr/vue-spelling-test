<template>
    <div>
        <h2>You got {{answersCorrect}} of 10 words spelled correctly </h2>
    </div>
</template>

<script>
import words from "../assets/words"
export default {
    data() {
        return {
            AllWords: words
        }
    },
    computed: {
        answersCorrect() {
            let correct = this.AllWords.filter(w => w.word === w.userInput)
            return correct.length
        }
    }
}
</script>
