<template>
  <div class="centered-container" v-if="showBlock" @click="stopTimer">
    <div class="block">
        <h1>Reaction time test</h1>
        <p>{{title}}</p>
    </div>
  </div>
</template>

<script>
export default {
    props: ['delay','title'],
    data(){
        return{
            showBlock: false,
            timer: null,
            reactionTime: 0
        }
    },
    mounted() {
        // console.log("mounted")
        setTimeout(() => {
            this.showBlock = true
            this.startTimer()
        },this.delay)
    },
    methods: {
        startTimer(){
            this.timer = setInterval(() => {
                this.reactionTime += 10
            },10)
        },
        stopTimer(){
            clearInterval(this.timer)
            console.log("timer",this.reactionTime)
        }
    }
}
</script>

<style scoped>

.centered-container{
    height: 700px;
    background: rgb(75, 158, 253);
    border-radius: 17px;
    color: white;
    display:flex;
    justify-content: center;
    align-items: center;
    line-height: 20px;
    margin: 20px 0;
}
h1{
    font-size: 80px;
}
p{
    font-size: 40px;
}
.isPlaying{
    background: red;
}

.isReady{
    background: rgb(85, 196, 63);
}


@media only screen and (max-width: 600px) {
h1{
    font-size: 30px;
}
p{
    font-size: 20px;
}
.centered-container{
    height: 500px;
}
}

</style>