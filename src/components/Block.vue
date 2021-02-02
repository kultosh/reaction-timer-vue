<template>
    <div class="block" v-if="showBlock" @click="stopTimer">
        Click Me
    </div>
</template>

<script>
export default {
    props: ['delay'],
    data () {
        return {
            showBlock: false,
            time: null,
            reactionTime: 0
        }
    },
    mounted() {
        console.log('mounted');
        
        setTimeout(() => {
            console.log(this.delay)
            this.showBlock = true
            this.startTimer()
        }, this.delay)
    },

    methods: {
        startTimer () {
            this.timer = setInterval(() => {this.reactionTime += 10}, 10)
            console.log(this.timer)
        },

        stopTimer () {
            clearInterval(this.timer)
            console.log(this.reactionTime)
        }
    }
}
</script>

<style scoped>
    .block {
        width: 400px;
        border-radius: 20px;
        background: #0faf87;
        color: white;
        text-align: center;
        padding: 100px 0;
        margin: 40px auto;
    }
</style>