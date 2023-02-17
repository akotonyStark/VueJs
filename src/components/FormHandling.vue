<template>
    <div :style="{backgroundColor:'#fafafa', height:'600px'}">
        <h2 v-bind:style="{marginTop: '50px'}">Job Application Form</h2>
        <pre>{{ JSON.stringify(formData, null, 2) }}</pre>
    <form>
        <div class="mt">
            <label for="name">Name</label>
            <input type="text" id="name" v-model="formData.name"/>
        </div>
        <div class="mt">
            <label for="profile">Profile Summary</label>
            <textarea type="text" id="profile" v-model="formData.profileSummary"></textarea>
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
                    jobLocation: []
                }
            }
        },
        methods: {

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

    input[type='text'], textarea, select{
        display: block;
        width: 400px;
        padding: 6px 12px;
        font-size: 14px;
        line-height: 1.4;
        color: #555;
        background-color: #fff;
    }

    .mt{
        margin-top: 20px;
    }
</style>