<template>
<form  @submit.prevent="submitting" >
    <label> Email: </label>
    <input type="email required" v-model="email">
    <label> password: </label>
        <div v-if="passwordError" class="error">
    Password should be 5 characters long    
     </div>
    <input type="email required" v-model="password">
    <p>
        Email: {{email}}
    </p>
    <p>
        password: {{password}}
    </p>

    <p>
        role: {{role}}
    </p>
        <p>
        terms Accepted: {{terms}}
    </p>
    <label> 
        <select v-model="role">
            <option value="developer"> Web Developer</option>
            <option value="designer"> Designer </option>
        </select>
    </label>

    <div class="terms">
        <input type="checkbox" v-model="terms" required>
        <label> Accept terms and conditions </label>
    </div>
    <label>Skills:</label>
    <input type="text" v-model="tempSkill" @keyup="addSkill">
    <div v-for="skill in skills" :key="skill" class="pill">
        <span @click="deleteSkill(skill)">{{skill}}</span> 
    </div>
    <div class="submit">
        <button> Create Account</button>
    </div>


</form>
  
</template>

<script>
export default {
    data(){
        return {
            email: 'test',
            password: '',
            role: '',
            terms: false,
            tempSkill: '',
            skills: [],
            passwordError: ''
        }
    },
    methods: {
        addSkill(e){
            if(e.key === ',' && this.tempSkill) {
                if(!this.skills.includes(this.tempSkill.slice(0,-1))){
                const localSkill = this.skills.push(this.tempSkill.slice(0,-1));
                }
                this.tempSkill='';
            }
        },
        deleteSkill(skill){
            this.skills = this.skills.filter(item => {
                return skill !==item
            });
        },
        submitting(){
            this.passwordError = this.password.length >5 ? '': "Password should be more this 5 characters"
            if(!this.passwordError){
            console.log("submiting");
            }

        }
    }
}
</script>

<style>
form {
    max-width: 420px;
    margin: 40px auto;
    background: white;
    text-align: left;
    padding: 40px;
    border-radius: 10px;
}
label {
    color: #aaa;
    display: inline-block;
    margin: 25px 0 15px;
    font-size: 0.6em;
    text-transform: uppercase;
    letter-spacing: 1px;
    font-weight: bold;
}
input, select {
    display: inline-block;
    padding: 5px 10px;
    width: 100%;
    box-sizing: border-box;
    border: none;
    border-bottom: 1px solid #ddd;
    color: #aaa;
}
input[type="checkbox"] {
    display: inline-block;
    width: 16px;
    margin: 0 10px 0 0;
    position: relative;
    top: 2px;
}
.pill  {
    margin-top: 10px;
    display: inline;
    background: grey;
}
button {
    background: blue;
    border: 0;
    padding: 10px 20px;
    margin-top: 20px;
    color: white;
    border-radius: 20px;
}
.submit {
    text-align: center;
}
.error {
    background: red;
    font-style: italic;
}

</style>