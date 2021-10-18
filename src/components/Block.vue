<template>
  <div class="block" v-if="isShowed" @click="stopTimer">
      Click Me
  </div>
</template>

<script>
export default {
    data(){
        return{
            isShowed: false,
            timer: null,
            reactTimer: 0,
        }
    },
    props:['delay'],
    mounted(){
        setTimeout(()=>{
            this.isShowed= true
            this.startTimer()
            }, this.delay)
    },
    methods:{
        startTimer(){
            this.timer = setInterval(()=>{
                this.reactTimer += 10
            }, 10)
        },
        stopTimer(){
            clearInterval(this.timer)
            this.$emit('end', this.reactTimer)
        }
    }
}
</script>

<style>
.block{
    width: 400px;
    border-radius: 20px;
    background: #0faf87;
    color: white;
    text-align: center;
    padding: 100px 0;
    margin: 40px auto;
}

</style>