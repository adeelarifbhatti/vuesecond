<template>
    <h1> Jobs </h1>
    <div v-for="course in courses" :key="course.id" class=job> 
        <router-link :to="{ name: 'JobsDetails',params: {id: course.name}}">
        {{course}}
        </router-link>

    </div>

</template>

<script>
export default {
    data() {
        return {
            courses: [ ]
        }
    },
    mounted() {
        fetch('http://mol.uio.no/api/v1/courses',{'method': 'get',
        headers: {
            'content-type': 'application/json'
         }
        })
        .then(res => res.json())
        .then(data => this.courses =data)
        .catch(err => console.log(err.message))
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