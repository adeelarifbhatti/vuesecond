<template>
    <div class="block" v-if="showBlock" @click="stopTimer()"> </div>  
</template>
<script>
export default {
    props: ['delay'],
    data() {
        return {
            showBlock: false,
            startTime: null,
            endTime: 0
        }
    },
    mounted() {
        console.log("component mounted")
        setTimeout(()=> {
            this.showBlock = true;
            this.startTimer();
            console.log(this.delay);
        },this.delay)
    },
    updated(){
        console.log("Component updated")
    },
    unmounted() {
        console.log("unmounted")
    },
    methods: {
        startTimer() {
            this.startTime = setInterval(() => {
                console.log(this.startTime);
                this.endTime += 10;
            },10);           
        },
        stopTimer(){
            console.log("Close windows");
            clearInterval(this.startTime);
            console.log("Time taken to click is", this.endTime);
            this.showBlock=false;
        }
    }  
}
</script>

<style>
.block {
    width: 700px;
    border-radius: 20px;
    background: green;
    padding: 100px 0;
    margin: 40px auto;

}

</style>