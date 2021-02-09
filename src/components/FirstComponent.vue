<template>
    <div class="backdrop" >
        <div class="first" :class="{ sale: theme === 'sale'}">
            <p>
                First
            </p>
            <h1>{{ header }}</h1>
            <p> {{ text }} </p>

        </div>
        <button @click="closeFirst"> Close </button>
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
.first {
    width: 82%;
    padding: 20px;
    margin: 50px auto;
    background: black;
    border-radius: 10px;
    color: yellow; 
}
.backdrop {
    top: 0;
    margin: 20px auto;
    position: fixed;
    background: rgb(161, 219, 186);
    width: 20%;
    height: 80%;
}
.first.sale {
    background: black;
    color: pink;
}
.first.sale h1 {
    color: blue;
}
</style>
