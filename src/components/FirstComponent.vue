<template>
    <div class="backdrop">
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
    props: ['header', 'text', 'theme'] 
}
</script>


<style>
.first {
    width: 100px;
    padding: 20px;
    margin: 100px auto;
    background: black;
    border-radius: 10px;
    color: yellow; 
}
.backdrop {
    top: 0;
    position: fixed;
    background: rgb(161, 219, 186);
    width: 20%;
    height: 20%;
}
.first.sale {
    background: black;
    color: pink;
}
.first.sale h1 {
    color: blue;
}
</style>
