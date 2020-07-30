<template>
    <div class="main">
     
        <a href="#" v-on:click.prevent="showForm = true" v-show="!showForm">Play Would You Rather?</a>
        
        <form v-on:submit.prevent="addNewWouldYouRather" v-show="showForm">
            <div class="form-entry">
                <label for="user">Name:</label>
                <input id="user" type="text" v-model.trim="newWouldYouRather.user" />
            </div>
            <div class="form-entry">
                <label for="optionOne">Food:</label>
                <input id="optionOne" type="text" v-model.trim="newWouldYouRather.optionOne" />
            </div>
            <div class="form-entry">
                <label for="optionTwo">Animal Bigger Than You:</label>
                <input id="optionTwo" type="text" v-model.trim="newWouldYouRather.optionTwo" />
            </div>
            <input type="submit" value="Submit" v-bind:disabled="!isFormValid" v-on:click="showText=true" v-show="!showText" />
        </form>
        <div class="wyr" v-for="answer in wyr " v-bind:key="answer.id" v-show="showText">
            <p>Hey {{answer.user}} would you rather...</p>
            <p>Eat 6 pounds of {{answer.optionOne}} for breakfast everyday</p>
            <p>Or have a {{answer.optionTwo}} as an indoor pet </p>
        </div>

    </div>
</template>

<script>
export default {
    name: "would-you-rather",
   

    data() {
        return {
            newWouldYouRather: {},
             showForm: false,
             showText: false,
             wyr: []
                
             
        }
    },
    computed: {
        isFormValid() {
            return this.newWouldYouRather.user && this.newWouldYouRather.optionOne
            && this.newWouldYouRather.optionTwo;
        }
        // add a reset that looks like play again?
    },
    methods: {
        addNewWouldYouRather() {
            this.wyr.unshift(this.newWouldYouRather);
        this.resetForm();
        },
        resetForm() {
            this.newWouldYouRather= {};
            this.showForm=false;
        }
    }
}
</script>

<style>
.main {
border: 1px black solid;
  border-radius: 6px;
  padding: 1rem;
  margin-right: 70px;
  margin-left: 70px;

}
a {
font-size: 30px;
}

label {
margin-right: 5px;
}
form {
  font-size: 25px;
}

.wyr {
font-family: Arial, Helvetica, sans-serif;
font-size: 20px;
color: black;
}
</style>
