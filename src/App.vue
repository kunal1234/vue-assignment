<template>
  <div id="app">
    <header class="header-wrap">
      <div class="container">
        <div class="inner">
          <div class="row"><a href="javascript:;" class="menu_mb"><span></span></a>
            <div class="hd-logo col-md-3 col-sm-3 col-xs-12">
                <router-link to="/">
                  <img src="/static/images/logo.png" alt="The Hour Glass - Leading Luxury Watch Retail Group" title="The Hour Glass - Leading Luxury Watch Retail Group">
                </router-link>
            </div>
            <!-- END : LOGO-->
            <div class="hd-menu col-md-6 col-sm-6 col-xs-12">
              <ul class="clearfix">
                <li><a href="#">Limited Edition Watches</a></li>
                <li><a href="#">Pre-owned Watches</a></li>
                <li><a href="#">Accessories</a></li>
                <li><a href="#">Journal</a></li>
              </ul>
              <ul class="mn-mb">
                <li><a href="#">Create Account</a></li>
                <li><a href="#">Login  </a></li>
              </ul>
            </div>
            <!-- END : MENU-->
            <div class="hd-cart col-md-3 col-sm-3 col-xs-12">
              <ul class="clearfix pull-right">
                <li>
                  <router-link to="/cart">
                    <i class="fa fa-shopping-cart"></i> <span>{{ cart.data.length }}</span>
                  </router-link>
                </li>
                <li><a href="#">Create Account</a></li>
                <li><a href="#">Login</a></li>
              </ul>
            </div>
            <!-- END : CART-->
          </div>
        </div>
      </div>
    </header>
    <!-- <div class="ui huge inverted top fixed menu">
      <div class="ui text container">
        <router-link to="/" class="header item">
          <img src="/static/moltin-light-hex.svg" class="ui mini image" style="margin-right: 1.5em;">Vue.js Store
        </router-link>
        <router-link to="/cart" class="right item">
          Cart ({{ cart.data.length }} items)
        </router-link>
      </div>
    </div> -->
    <router-view :cart="cart" @cart-updated="onCartUpdated"></router-view>
  </div>
</template>

<script>
import MoltinService from './services/moltin.js'

export default {
  name: 'app',
  data () {
    return {
      cart: {
        data: []
      }
    }
  },
  beforeMount () {
    MoltinService.getCart().then((response) => {
      this.cart = response
    })
  },
  methods: {
    onCartUpdated (cart) {
      this.cart = cart
    }
  }
}
</script>

<style>
</style>
