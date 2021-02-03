<template>
    <div>
        <p v-if="score>0">Reaction time - {{score}} ms </p>
        <p class="rank">{{rank}}</p>
    </div>
</template>

<script>
export default {
    props: ['score'],

    data () {
        return {
            rank: null
        }
    },

    mounted() {
        if(this.score <= 200)
        {
            this.rank = "You are quick!"
        }
        else if (this.score <=400)
        {
            this.rank = "You are quite fast!"
        }
        else
        {
            this.rank = "You are slow as Snail!"
        }
    },
}
</script>

<style scoped>
 .rank {
     font-size: 1.4em;
     color: #0faf87;
     font-weight: bold;
 }
</style>