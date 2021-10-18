<template>
  <p>Your score is {{ score }} ms</p>
  <p class="rank">{{rank}}</p>
</template>

<script>
export default {
    props:['score'],
    data(){
        return{
            rank: null,
        }
    },
    mounted(){
        if(this.score < 250){
            this.rank = "Fast Hand"
        }else if(this.score < 400){
            this.rank = "Good One"
        }else{
            this.rank = "Slow Hand"
        }
    }
}
</script>

<style>
.rank{
    font-size: 1.4em;
    columns: #0faf87;
    font-weight: bold;
}
</style>