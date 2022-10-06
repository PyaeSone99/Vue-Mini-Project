<template>
    <p>The result is {{score}}ms</p>
    <div v-if="score <300">
        <p>You are too Fast</p>
    </div>
    <div v-else-if="score < 600 && score>301">
        <p>You are Normal</p>
    </div>
    <div v-else>
        <p>Your are too Slow</p>
    </div>
</template>

<script>
export default {
    props : ["score"],
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>