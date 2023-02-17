<template>
    <div :style="{backgroundColor:'#fafafa', height:'1200px'}">
        <h2 v-bind:style="{marginTop: '50px'}">Job Application Form</h2>
        <pre>{{ JSON.stringify(formData, null, 2) }}</pre>
    <form @submit.prevent="submitFormData">
        <div class="mt">
            <label for="name">Name</label>
            <input type="text" id="name" v-model.trim="formData.name"/>
        </div>
        <div class="mt">
            <label for="age">Age</label>
            <input type="number" id="age" v-model.number="formData.age"/>
        </div>
        <div class="mt">
            <label for="profile">Profile Summary</label>
            <!-- The lazy modifier doesn't bind on every key stroke -->
            <textarea type="text" id="profile" @keyup.enter="printSomethingOnKeyEvent" v-model.lazy="formData.profileSummary"></textarea>
        </div>
        <div class="mt">
            <label for="country">Country</label>
            <select id="country" v-model="formData.country">
                <option value="">Select a country</option>
                <option value="GH">Ghana</option>
                <option value="US">United States</option>
                <option value="CA">Canada</option>
            </select>
        </div>
        <div class="mt">
            <label for="location">Job Location</label>
            <select id="location" multiple v-model="formData.jobLocation">
                <option value="GH">Ghana</option>
                <option value="US">United States</option>
                <option value="CA">Canada</option>
            </select>
        </div>
        <div class="mt">
            <input type="checkbox" id="remoteWork" v-model="formData.remoteWork" true-value="Yes" false-value="No"/>
            <label for="remoteWork">Open to remote work?</label>
        </div>
        <div class="mt">
            <label>Tech Stack</label>
            <input type="checkbox" id="react" v-model="formData.skillSet" value="ReactJS"/>
            <label for="react">ReactJS</label>
            <input type="checkbox" id="vue" v-model="formData.skillSet" value="VueJS"/>
            <label for="vue">VueJS</label>
            <input type="checkbox" id="angular" v-model="formData.skillSet" value="AngularJs"/>
            <label for="angular">AngularJs</label>
            
        </div>
        <div class="mt">
            <label>Years of Experience</label>
            <input type="radio" id="0-2" v-model="formData.yearsOfExperience" value="0-2"/>
            <label for="0-2">0 to 2 years</label>
            <input type="radio" id="3-5" v-model="formData.yearsOfExperience" value="3-5"/>
            <label for="3-5">3 to 5 years</label>
            <input type="radio" id="6-10" v-model="formData.yearsOfExperience" value="6-10"/>
            <label for="6-10">6 or more years</label>
        </div>
        <div class="mt">
            <button>Submit</button>
        </div>

    </form>
    </div>
    

</template>



<script>
    export default{
        name: 'FormHandling',
        data(){
            return {
                formData: {
                    name: '',
                    profileSummary: '',
                    country:'',
                    jobLocation: [],
                    remoteWork: false,
                    skillSet: [],
                    yearsOfExperience:'',
                    age: ""
                }
            }
        },
        methods: {
            submitFormData(){
                //event.preventDefault()
                console.log(this.formData)
            },

            printSomethingOnKeyEvent(e){
                console.log('Printing event:', e)
            }
        }
    }
</script>


<style scoped>
    label{
        font-weight: bold;
        display: flex;
        margin-bottom: 5px;
    }

    input + label {
        font-weight: bold;
        display: inline-flex;
        margin-right: 20px;
    }

    input[type="text"], input[type="number"], button, textarea, select{
        display: block;
        width: 400px;
        padding: 6px 12px;
        font-size: 14px;
        line-height: 1.4;
        color: #555;
        /* background-color: #fff; */
    }

    .mt{
        margin-top: 20px;
    }
</style>