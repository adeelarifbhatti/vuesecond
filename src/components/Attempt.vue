<template>
    <div class="block" v-if="showBlock"> </div>
  
</template>

<script>

export default {
    props: ['delay'],
    data() {
        return {
            showBlock: false
        }
    },
    mounted() {
        console.log("component mounted")
        setTimeout(()=> {
            this.showBlock = true
            console.log(this.delay)
        },this.delay)
    },
    updated(){
        console.log("Component updated")
    },
    unmounted() {
        console.log("unmounted")
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