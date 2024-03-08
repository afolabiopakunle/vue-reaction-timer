<template>
  <h1>Ninja Reaction Timer</h1>
  <button :disabled="isPlaying" @click="start">{{ isPlaying ? 'Stop' : 'Play' }}</button>
  <BlockComponent v-if="isPlaying" :delay="delay" @end="ended" />
  <ResultsComponent :score="score" v-if="score"/>
</template>

<script>
import BlockComponent from './components/BlockComponent.vue';
import ResultsComponent from './components/ResultsComponent.vue';

export default {
  name: 'App',
  components: {
    BlockComponent,
    ResultsComponent,
  },
  data() {
    return {
      isPlaying: false,
      delay: null,
      score: null,
    }
  },
  methods: {
   start() {
    this.delay = 2000 + Math.floor(Math.random() * 5000)
    this.isPlaying = !this.isPlaying
   },

   ended(time) {
      console.log('Ended', time);
      this.score = time;
   }
  }
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
