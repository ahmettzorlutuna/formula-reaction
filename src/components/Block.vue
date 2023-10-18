<template>
  <div class="centered-container" ref="container" v-if="showBlock">
    <div class="block">
        <h1>Reaction Time Test!</h1>
        <p>Improve your reflexes</p>
    </div>
  </div>
</template>

<script>
export default {
    props: ['delay'],
    data(){
        return{
            showBlock: false
        }
    },
    mounted() {
        console.log("mounted block component")
        setTimeout(() => {
            this.showBlock = true
            console.log(this.delay)
        },this.delay)
    },
    updated() {
        console.log("compoennt updated")
    },
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
    background: rgb(196, 163, 63);
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