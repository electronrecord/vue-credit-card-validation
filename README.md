# vue-credit-card-validation

[![npm](https://img.shields.io/npm/v/vue-credit-card-validation.svg)](https://www.npmjs.com/package/vue-credit-card-validation)
[![vue2](https://img.shields.io/badge/vue-2.x-brightgreen.svg)](https://vuejs.org/)

A dependency-free Vue plugin for formatting and validating credit card form fields.

How to use it in a real Vue web app:

1. Install it with 
npm install vue-credit-card-validation

2. go to you app.js file (main js app config file)
and add:

import VueCardFormat from 'vue-credit-card-validation'

Vue.use(VueCardFormat)

3. go to your component and attach the directive to the input field that you want to validate
(in my case was just card number):

<inpu class=""
      v-model="card.number"
      v-cardformat:formatCardNumber />
      
4. to validate the card number, we use the object this.$cardFormat:

methods: {
  submit () {
    const val = this.$cardFormat.validateCardNumber(this.card.pan)
    // now val is true or false depending on the validation
    }
}

NOTE: u might get an error in the console with some "addEventListener" issue,
this is due to the fact that in the directive the input.nodeName is declared with lowerCase,
but in my case, the string was with capital letters, like INPUT.

U can contact me for further details.
