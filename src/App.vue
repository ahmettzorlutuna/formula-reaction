<template>
  <h1>Welcome to reaction test!</h1>
  <Block v-if="isWaiting" @click="start" style="cursor: pointer;"/>
  <!-- <Block v-if="isReady" style="cursor: pointer;"/> -->
  <Block v-if="isPlaying" :class="{ isPlaying: isPlaying}" :delay="delay" style="cursor: pointer;"/>

  <!-- <Block :delay="delay" @click="start" :class="{ isPlaying: isPlaying}"/> -->
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
      this.isWaiting= false
      this.isReady = true
      this.delay = 2000 + Math.random() * 3000; 
      console.log(this.delay)
    }
  },
  data() {
    return {
      isPlaying: false,
      isWaiting: true,
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
