<template>
  <h1>Welcome to reaction test!</h1>
  <Block v-if="isPlaying" :class="{ isPlaying: isPlaying}" :delay="delay" style="cursor: pointer;"/>
  <Block @click="start" style="cursor: pointer;" :class="{isReady : isPlaying}"/>
  <Block v-if="isReady" style="cursor: pointer;" :class="{isWaiting: isPlaying}"/>
</template>

<script>
import Block from './components/Block.vue'

export default {
  name: 'App',
  components: {
    Block
  },
  methods: {
    start(){
      this.isPlaying= true
      this.isReady = true
      this.delay = 2000 + Math.random() * 3000;
      console.log(this.delay)
    }
  },
  data() {
    return {
      isPlaying: false,
      isReady: false,
      delay: null
    }
  },
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
