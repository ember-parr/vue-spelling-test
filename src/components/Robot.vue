<template>
    <div>
        <p>Word {{ word.id }} of 10</p>
        <img alt="Sound Icon" src="../assets/sound-icon.png" class="soundIcon" />
        <p>Say Word</p>
        <p>{{ word.word }}</p>
    </div>
</template>

<script >
export default {
    props: ["word"]
}

</script>

<style scoped>
.soundIcon {
    width: 15%;
    height: auto;
}
</style>