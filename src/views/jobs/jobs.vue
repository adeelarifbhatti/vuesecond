<template>
    <h1> Jobs </h1>
    <div v-for="job in jobs" :key="job.id" class=job> 
        <router-link :to="{ name: 'JobsDetails',params: {id: job.id}}">
        {{job.title}}
        </router-link>

    </div>

</template>

<script>
export default {
    data() {
        return {
            jobs: [
                
                   { title: "System Admin", id: 1, details: 'lorem'},
                   { title: "System Admin", id: 2, details: 'lorem'},
                   { title: "System Admin", id: 3, details: 'lorem'}
            ]
        }
    }

}
</script>

<style>
.job {

    background: grey;
    padding: 10px;
    margin: 20px auto;
    max-width: 300px;
    cursor: pointer;
    border-radius: 20px;
}
.job:hover {
    background: rgb(145, 145, 160);
}

</style>