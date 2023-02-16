<template>
    <div class="body">
        <h2 class="underline" v-bind:class="{
        error: error,
        titler: !isTitle
    }">Login Form</h2>
    <p v-bind:class="error ? ['error', 'underline'] : 'success'" v-bind:hidden="isHidden">{{
        error? "Error occured": ""
    }}</p>
    <!-- rarely use v-html directive. be very cautious -->
    <div v-html=usernameContent></div>
    <label><b>Password:</b> </label>
    <input type="password" placeholder="password" v-bind:id="password" :class="isLabel" /><br /><br />
    <button v-bind:disabled="error">Login</button><br /><br />

    <h2 v-bind:style="{
        color: highlightColor,
        fontSize: headerSize,
        padding: '20px'
    }">Inline Styling</h2>

    <h2 v-bind:style="headerStyles">Another Inline Styling</h2>
    </div>
 


</template>


<script>

export default {
    name: "LoginForm",
    data() {
        return {
            username: '',
            password: 'asdasdasd',
            usernameContent: '<b>Username: </b> <input type="text"  placeholder="username"/><br/>',
            isDisabled: true,
            isHidden: false,
            error: false,
            isHeader: true,
            isTitle: true,
            isLabel: false,
            highlightColor: 'orange',
            headerSize: '50px',
            headerStyles: {
                color: 'red',
                fontSize: '50px',
                padding: '0px'

            }
        }
    },

    methods: {
        handleUsername(e) {
            console.log(e.target.value)
        }
    }
}
</script>


<style>

.body{
    background-color: chocolate;
}
.underline {
    text-decoration: underline;
}

.error {
    color: darkred;
    font-weight: 900;
}

.success {
    color: green;
    font-weight: 900;
}

.header {
    font-size: larger;
}

.titler {
    text-decoration: line-through;
}

.label {
    color: '#080808'
}
</style>