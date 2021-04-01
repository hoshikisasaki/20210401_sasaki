<template>

    <header id="top-header">
        <div class="flex">
          <h1 class="header-logo">estra inc.</h1>
          <nav class="header-nav">
            <ul>
              <li><a href="#">home</a></li>
              <li><a href="#">about</a></li>
              <li><a href="#">service</a></li>
              <li><a href="#">works</a></li>
              <li><a href="#">price</a></li>
              <li><a href="#">contact</a></li>
            </ul>
          </nav>
        </div>
        <div id="hamburger" :class="{'menu-hambuger':ActiveBtn}" @click='ActiveBtn = !ActiveBtn'>
          <span :class="{'close_btn1':ActiveBtn}"></span>
          <span :class="{'close_btn2':ActiveBtn}"></span>
          <span :class="{'close_btn3':ActiveBtn}"></span>
        </div>
        <transition name="menu">
      <div class="menu" v-show="ActiveBtn">
        <p class="menu-ttl">estra inc.</p>
       <ul>
         <li><a href="">home</a></li>
         <li><a href="">about</a></li>
         <li><a href="">service</a></li>
         <li><a href="">works</a></li>
         <li><a href="">price</a></li>
         <li><a href="">contact</a></li>
       </ul>
      </div><!-- /.men -->
        </transition>
    </header>

</template>
<script>
export default {
  data(){
    return{
      ActiveBtn:false
    }
  }
}
</script>

<style scoped>

 #hamburger {
  display: none;
}

#top-header {
  height: 70px;
  line-height: 70px;
  background: rgba(0, 0, 0, 1);
}

.header-logo {
  font-size: 20px;
  font-weight: bold;
  margin-left: 35px;
  color: #fff;
  line-height: 70px;
}

.header-nav li {
  display: inline-block;
  margin-right: 35px;
  font-size: 16px;
}

.header-nav a {
  color: #fff;
}

@media screen and (max-width: 768px) {
  #hamburger {
    width: 40px;
    height: 40px;
    position: absolute;
    cursor: pointer;
    z-index: 1001;
    top: 15px;
    right: 20px;
    transition: 0.4s;
    display: block;
  }
  #hamburger span {
    display: block;
    width: 35px;
    height: 2px;
    background-color: #fff;
    transition: 0.8s;
  }
  #hamburger span:nth-of-type(1) {
    position: absolute;
    top: 10px;
    left: 2px;
  }
  #hamburger span:nth-of-type(2) {
    position: absolute;
    top: 20px;
    left: 2px;
  }
  #hamburger span:nth-of-type(3) {
    position: absolute;
    top: 30px;
    left: 2px;
  }
  .close_btn1{
   transform: translateY(10px) rotate(-45deg);
  transition: 0.4s ease;
    background-color: black !important;
  }
  .close_btn2{
 transition: 0.4s ease;
  opacity: 0;
  }
  .close_btn3{
 transform: translateY(-10px) rotate(45deg);
  transition: 0.4s ease;
  background-color: black !important;
  }
 .menu{
   display: block;
   width: 100%;
   height: 100vh;
   z-index: 1000;
   background-color: #fff;
   position: fixed;
   top: 0;
 }
 .menu-ttl{
   margin: 40px 20px;
    font-size: 2.2rem;
    color: #333333;
    text-align: left;
    font-weight: bold;
 }
 .menu li a {
    color: #333333;
    margin: 15px;
    padding: 5px;
    border-bottom: 0.5px solid #2662d5;
    text-decoration: none;
    display: block;
 }
 .menu li{
   width: 100%;
   text-align: left;
 }
 .menu-enter-active,.menu-leave-active{
transition: opacity 0.4s;
 }
 .menu-enter,.menu-leave-to{
   opacity: 0;
 }
 .menu-leave,.menu-enter-to{
   opacity: 1;
 }
 .menu-hambuger{
   position: fixed !important;
 }
}
</style>