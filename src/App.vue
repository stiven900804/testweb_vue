﻿<template>
  <div>
    <div class="app-head">
      <div class="app-head-inner">
        <router-link :to="{name: 'index'}" class="head-logo">
          <img src="./assets/logo.png">
        </router-link>
        <div class="head-nav">
          <ul class="nav-list">
            <li @click="showDialog('isShowLogin')">登录</li>
            <li class="nav-pile">|</li>
            <li @click="showDialog('isShowReg')">注册</li>
            <li class="nav-pile">|</li>
            <li @click="showDialog('isShowAbout')">关于</li>
          </ul>
        </div>  
      </div>
    </div>
    <div class="container">
      <keep-alive>
        <router-view></router-view>
      </keep-alive>
    </div>
    <div class="app-foot">
      <p>© 2025 copyright 三剑客网上购物商城 @陈重 </p>
    </div>
    <this-dialog :is-show="isShowAbout" @on-close="hideDialog('isShowAbout')">
      <p>本平台主要销售电器类商品的销售。如果遇到问题，请联系平台开发者的微信codehome6，从而获取技术支持。</p>
    </this-dialog>
    <this-dialog :is-show="isShowLogin" @on-close="hideDialog('isShowLogin')">
      <login-form @on-success="" @on-error=""></login-form>
    </this-dialog>
  </div>
</template>

<script>
import ThisDialog from '@/components/base/dialog'
import LoginForm from '@/components/logForm'

export default {
  name: 'app',
  components: {
    ThisDialog,
    LoginForm
  },
  data: function () {
    return {
      isShowAbout: false,
      isShowLogin: false,
      isShowReg: false
    }
  },
  methods: {
    showDialog (param) {
      this[param] = true
    },
    hideDialog (param) {
      this[param] = false
    }
  }
}
</script>

<style>
/* http://meyerweb.com/eric/tools/css/reset/ 
   v3.0 | 20120126
   License: none (public domain)
*/

html, body, div, span, applet, object, iframe,
h1, h2, h3, h4, h5, h6, p, blockquote, pre,
a, abbr, acronym, address, big, cite, code,
del, dfn, em, img, ins, kbd, q, s, samp,
small, strike, strong, sub, sup, tt, var,
b, u, i, center,
dl, dt, dd, ol, ul, li,
fieldset, form, label, legend,
table, caption, tbody, tfoot, thead, tr, th, td,
article, aside, canvas, details, embed, 
figure, figcaption, footer, header, hgroup, 
menu, nav, output, ruby, section, summary,
time, mark, audio, video {
  margin: 0;
  padding: 0;
  border: 0;
  font-size: 100%;
  font: inherit;
  vertical-align: baseline;
}
/* HTML5 display-role reset for older browsers */
article, aside, details, figcaption, figure, 
footer, header, hgroup, menu, nav, section {
  display: block;
}
body {
  line-height: 1;
}
ol, ul {
  list-style: none;
}
blockquote, q {
  quotes: none;
}
blockquote:before, blockquote:after,
q:before, q:after {
  content: '';
  content: none;
}
table {
  border-collapse: collapse;
  border-spacing: 0;
}
a {
  color: inherit;
  text-decoration: none;
}
body {
  background: #f0f2f5;
  font-family: "Helvetica Neue",Helvetica,Arial,"Hiragino Sans GB","Hiragino Sans GB W3","Microsoft YaHei UI","Microsoft YaHei","WenQuanYi Micro Hei",sans-serif;
  font-size: 14px;
  color: #444;
}
.app-head {
  background: #363636;
  color: #b2b2b2;
  height: 90px;
  line-height: 90px;
  width: 100%;
}
.app-head-inner {
  width: 1000px;
  margin: 0 auto;
}
.head-logo {
  float: left;
  margin-top: 20px;
}
.head-logo img {
  width: 50px;
}
.head-nav {
  float: right;
}
.head-nav ul {
  overflow: hidden;
}
.head-nav li {
  cursor: pointer;
  float: left;
}
.nav-pile {
  padding: 0 10px;
}
.app-foot {
  text-align: center;
  height: 80px;
  width: 100%;
  line-height: 80px;
  background: #e3e4e8;
  clear: both;
  margin-top: 30px;
}
.container {
  width: 1000px;
  margin: 0 auto;
}
.hr {
  height: 1px;
  width: 100%;
  background: #ddd;
}
.button {
  background: #4fc08d;
  color: #fff;
  display: inline-block;
  padding: 10px 20px;
  cursor: pointer;
  border-radius: 5px;
}
.button:hover {
  background: #4fc08d;
}
.g-form {

}
.g-form-line {
  padding: 15px 0;
}
.g-form-label {
  width: 100px;
  font-size: 16px;
  display: inline-block;
}
.g-form-input {
  display: inline-block;
}
.g-form-input input {
  height: 30px;
  width: 200px;
  line-height: 30px;
  vertical-align: middle;
  padding: 0 10px;
  border: 1px solid #ccc;
}
.g-form-btn {
  padding-left: 100px;
}
</style>
