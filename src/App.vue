<template>
<h1>Ninja Reaction Timer</h1>
<button @click="start" :disabled="isPlaying">Click</button>

<BlockComponent v-if="isPlaying" :delay="delay" @end="endGame"/>
<ResultComponent :score="score" :showResult="showResult"/>
</template>

<script>
import BlockComponent from './components/BlockComponent.vue'
import ResultComponent from './components/ResultComponent.vue';
export default {
    name: 'App',
    components: {BlockComponent,ResultComponent},
    data(){
      return{
        isPlaying: false,
        delay: null,
        score : null,
        showResult: false,
      }
    },
    methods: {
        start: function () {
          this.delay = 2000 + Math.random() * 5000
          this.isPlaying = true
          this.showResult = false
        },
        endGame(reactionTime){
          this.score = reactionTime
          this.isPlaying = false
          this.showResult = true
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
    color: #444;
    margin-top: 60px;
}
</style>
