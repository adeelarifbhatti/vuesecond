<template>
    <div class="backdrop" @click.self="closeFirst">
        <div class="first" :class="{ sale: theme === 'sale'}">
            <p>
                First
            </p>
            <h1>{{ header }}</h1>
            <p> {{ text }} </p>
        </div>
     </div>
</template>

<script>
export default {
    props: ['header', 'text', 'theme'],
    methods: {
        closeFirst(){
            this.$emit('close');
        }
    }
}
</script>


<style>

.backdrop {
    position: relative;
    background: rgb(161, 219, 186);
    width: 45vh;
    height: 40vh;
}
.first {
    position: absolute;
    top: 10%;
    right: 2%;
    left: 2%;
    bottom: 20%;
    background: black;
    border-radius: 10px;
    color: yellow; 
}
.first.sale {
    background: black;
    color: pink;
}
.first.sale h1 {
    color: blue;
}
</style>
