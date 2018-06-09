<template>
    <div class="row">
      <div class="col-md-12">
        <form>

          <p>{{ errors }}</p>
<h1>Checkout</h1>
<hr />
<div class="row">
  <div class="col-sm-12 col-md-4">
      <h4>Shipping Address</h4>
      <hr />  
    <!-- Customer -->     
        <div class="form-group input-wrapper" v-bind:class="{ 'required': checkoutData.customer.email === '' && validate === true}">
          <label for="name">Email <span class="error-message"> is required field</span></label>
          <input type="email" v-bind:disabled="disabledFeild" class="form-control" id="email" @focus="floatingLabel" @keypress="floatingLabel" @blur="floatingLabel" v-model="checkoutData.customer.email" required autocomplete="off">
        </div>
        <div class="form-group input-wrapper"  v-bind:class="{ 'required': checkoutData.customer.password === '' && validate === true}">
          <label for="password">Password <span class="error-message">is required field</span></label>
          <input type="password" v-bind:disabled="disabledFeild" class="form-control" id="password" @focus="floatingLabel" @keypress="floatingLabel" @blur="floatingLabel" v-model="checkoutData.customer.password" required autocomplete="off" />
        </div>
        <div class="form-group">
          <p>
            you already have an account with us. Sign in or continue as guest.
          </p>
        </div>
        <div class="form-group">
          <button @click="loginUser" v-bind:disabled="disabledFeild" type="button" class="btn btn-gold mr-3"><span>Login</span></button>
          <a href="#" v-show="!disabledFeild"> <span>Forgot your password?</span></a>
        </div>
        <hr />
    <!-- Customer -->
<!-- Shipping Address -->
        <div class="form-group input-wrapper"  v-bind:class="{ 'has-floating-label': checkoutData.shipping_address.first_name !== '' }">
          <label for="billing-first-name">First Name <span class="error-message"> is required field</span></label>
          <input type="text" class="form-control" id="billing-first-name" @focus="floatingLabel" @keypress="floatingLabel" @blur="floatingLabel" v-model="checkoutData.shipping_address.first_name" required autocomplete="off">
        </div>
        <div class="form-group input-wrapper"  v-bind:class="{ 'has-floating-label': checkoutData.shipping_address.last_name !== '' }">
          <label for="billing-last-name">Last Name <span class="error-message"> is required field</span></label>
          <input type="text" class="form-control" id="billing-last-name" @focus="floatingLabel" @keypress="floatingLabel" @blur="floatingLabel" v-model="checkoutData.shipping_address.last_name" required autocomplete="off">
        </div>
        <div class="form-group input-wrapper"  v-bind:class="{ 'has-floating-label': checkoutData.shipping_address.county !== '' }">
          <label for="billing-county">County <span class="error-message"> is required field</span></label>
          <input type="text" class="form-control" id="billing-county" @focus="floatingLabel" @keypress="floatingLabel" @blur="floatingLabel" v-model="checkoutData.shipping_address.county" required autocomplete="off">
        </div>
        <div class="form-group input-wrapper"  v-bind:class="{ 'has-floating-label': checkoutData.shipping_address.line_1 !== '' }">
          <label for="billing-line-1">Address Line 1 <span class="error-message"> is required field</span></label>
          <input type="text" class="form-control" id="billing-line-1" @focus="floatingLabel" @keypress="floatingLabel" @blur="floatingLabel" v-model="checkoutData.shipping_address.line_1" required autocomplete="off">
        </div>
        <div class="form-group input-wrapper"  v-bind:class="{ 'has-floating-label': checkoutData.shipping_address.line_2 !== '' }">
          <label for="billing-line-2">Address Line 2 <span class="error-message"> is required field</span></label>
          <input type="text" class="form-control" id="billing-line-2" @focus="floatingLabel" @keypress="floatingLabel" @blur="floatingLabel" v-model="checkoutData.shipping_address.line_2" required autocomplete="off">
        </div>


        <div class="form-group input-wrapper"  v-bind:class="{ 'has-floating-label': checkoutData.shipping_address.city !== '' }">
          <label for="billing-city">City <span class="error-message"> is required field</span></label>
          <input type="text" class="form-control" id="billing-city" @focus="floatingLabel" @keypress="floatingLabel" @blur="floatingLabel" v-model="checkoutData.shipping_address.city" required autocomplete="off">
        </div>
        
        <div class="form-group input-wrapper"  v-bind:class="{ 'has-floating-label': checkoutData.shipping_address.postcode !== '' }">
          <label for="billing-post-code">Post Code <span class="error-message"> is required field</span></label>
          <input type="text" class="form-control" id="billing-post-code" @focus="floatingLabel" @keypress="floatingLabel" @blur="floatingLabel" v-model="checkoutData.shipping_address.postcode" required autocomplete="off">
        </div>
        <div class="form-group input-wrapper"  v-bind:class="{ 'has-floating-label': checkoutData.shipping_address.country !== '' }">
          <label for="billing-country">Country <span class="error-message"> is required field</span></label>
          <input type="text" class="form-control" id="billing-country" @focus="floatingLabel" @keypress="floatingLabel" @blur="floatingLabel" v-model="checkoutData.shipping_address.country" required autocomplete="off">
        </div>
        <div class="form-group input-wrapper"  v-bind:class="{ 'has-floating-label': checkoutData.shipping_address.phone !== '' }">
          <label for="phone">Phone Number <span class="error-message"> is required field</span></label>
          <input type="text" class="form-control" id="phone" @focus="floatingLabel" @keypress="floatingLabel" @blur="floatingLabel" v-model="checkoutData.shipping_address.phone" required autocomplete="off">
        </div>
    <!-- Shipping Address -->
  </div>
  <div class="col-sm-12 col-md-4">
        <h4>Shipping Method</h4>
        <hr/>
        <!-- Shipping Method -->
        <div>
            <table class="table">
              <tbody>
                <tr>
                  <td><input type="radio" name="shipping" id="fixed" checked/></td>
                  <td><strong>$0.00</strong></td>
                  <td>Fixed</td>
                  <td>Flat Rate</td>
                </tr>
                <tr>
                  <td><input type="radio" name="shipping" id="table-rate"/></td>
                  <td><strong>$0.00</strong></td>
                  <td>Table Rate</td>
                  <td>Best Way</td>
                </tr>
              </tbody>
            </table>
        </div>
        <!-- Shipping Method -->
  </div>
  <div class="col-sm-12 col-md-4">
<h4>Order Summery</h4>
        <hr/>
  </div>
</div>
        </form>
      </div>
    </div>
</template>
<script>
import MoltinService from '../services/moltin.js'
import userData from '../user-data.json'

export default {
  name: 'product',
  data () {
    return {
      errors: '',
      checkoutData: {
        customer: {
          name: '',
          email: '',
          password: ''
        },
        shipping_address: {
          first_name: '',
          last_name: '',
          line_1: '',
          line_2: '',
          city: '',
          postcode: '',
          county: '',
          country: '',
          phone: ''
        }
      },
      userData: userData,
      validate: false,
      disabledFeild: false
    }
  },
  methods: {
    checkout () {
      MoltinService.checkout(this.checkoutData).then((response) => {
        this.$router.push('/payments/' + response.data.id)
      }).catch((err) => {
        this.errors = 'There was a problem checking out' + err
      })
    },
    floatingLabel () {
      if (event.type === 'focus') {
        event.path[1].className = 'form-group input-wrapper has-floating-label'
      }
      if (event.type === 'blur' && event.target.value === '') {
        event.path[1].className = 'form-group input-wrapper required'
      }
      if (event.type === 'keypress') {
        event.path[1].className = 'form-group input-wrapper has-floating-label'
      }
    },
    loginUser () {
      if (this.checkoutData.customer.email !== '' && this.checkoutData.customer.password !== '') {
        for (let user in this.userData) {
          if (this.checkoutData.customer.email === this.userData[user].customer.email && this.checkoutData.customer.password === this.userData[user].customer.password) {
            this.checkoutData = this.userData[user]
            this.disabledFeild = true
          }
        }
        if (this.checkoutData.shipping_address.first_name === '') {
          alert('Please enter valid Username and Password.')
        }
      } else {
        this.validate = true
      }
    }
  }
}
</script>
<style></style>
