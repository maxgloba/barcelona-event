<template>
  <div class="page page-barcelona">
    <Header />
    <Banner :loaded="loaded"/>
    <Whatis v-if="loaded" />
    <Points v-if="loaded" />
    <Howdid v-if="loaded" />
    <Whogoes v-if="loaded" />
    <Experience v-if="loaded" />
    <Topics v-if="loaded" />
    <Schedule v-if="loaded" />
    <Testimonials v-if="loaded" />
    <Moneyback v-if="loaded" />
    <Footer v-if="loaded" />
  </div>
</template>
<script>
export default {
  data() {
    return {
      loaded: false,
      live: true
    }
  },
  methods: {
    grafitiAnim(){
      const grafitis = document.querySelectorAll('.grafiti')
      grafitis.forEach(grafiti => {
        const grafitiTop = grafiti.offsetTop + grafiti.parentNode.offsetTop - window.innerHeight
        if(window.scrollY > grafitiTop){
          grafiti.classList.add('active')
        }
      })
    }
  },
  mounted() {
    this.loaded = true
    setTimeout(()=>{
      window.onscroll = e => this.grafitiAnim()
    }, 1000);
  }
}
</script>
<style lang="scss">
@font-face {
  font-family: 'PP Pangram Sans';
  src: url('@/assets/fonts/pangram/Pangram-Regular.eot');
  src: local('PP Pangram Sans'),
       url('@/assets/fonts/pangram/Pangram-Regular.woff') format('woff'),
       url('@/assets/fonts/pangram/Pangram-Regular.ttf') format('truetype'),
       url('@/assets/fonts/pangram/Pangram-Regular.svg') format('svg');
  font-weight: 400;
  font-style: normal;
}
@font-face {
  font-family: 'PP Pangram Sans';
  src: url('@/assets/fonts/pangram/Pangram-Medium.eot');
  src: local('PP Pangram Sans'),
       url('@/assets/fonts/pangram/Pangram-Medium.woff') format('woff'),
       url('@/assets/fonts/pangram/Pangram-Medium.ttf') format('truetype'),
       url('@/assets/fonts/pangram/Pangram-Medium.svg') format('svg');
  font-weight: 500;
  font-style: normal;
}
@font-face {
  font-family: 'PP Pangram Sans';
  src: url('@/assets/fonts/pangram/Pangram-Bold.eot');
  src: local('PP Pangram Sans'),
       url('@/assets/fonts/pangram/Pangram-Bold.woff') format('woff'),
       url('@/assets/fonts/pangram/Pangram-Bold.ttf') format('truetype'),
       url('@/assets/fonts/pangram/Pangram-Bold.svg') format('svg');
  font-weight: 700;
  font-style: normal;
}
.page-barcelona{
  background: #0B0B0B;
  color: #fff;
  position: relative;
  overflow: hidden;
  * {
    font-family: 'PP Pangram Sans';
  }
  img{
    max-width: 100%;
  }
  section{
    position: relative;
  }
  .container {
    width: 100%;
    padding-left: 10px;
    padding-right: 10px;
    margin-left: auto;
    margin-right: auto;
    position: relative;
    z-index: 2;
    @media (min-width: 1200px) {
      max-width: 1200px;
    }
  }
}
.sqrs{
  span{
    display: block;
    border: 2px solid #FF3D00;
    background-color: transparent;
    width: 15px;
    height: 15px;
    animation-name: sqrBg;
    animation-duration: 1s;
    animation-iteration-count: infinite;
    animation-timing-function: ease;
    @media(min-width:768px){
      width: 30px;
      height: 30px;
    }
    &:nth-child(1){animation-delay: 0s;}
    &:nth-child(2){animation-delay: .25s;}
    &:nth-child(3){animation-delay: .5s;}
  }
  &-right{
    margin-left: 14px;
    margin-top: -2px;
    margin-bottom: -2px;
    @media(min-width:768px){
      margin-left: 28px;
    }
  }
}
@keyframes sqrBg {
  50% {
    background-color: #FF3D00;
  }
}
.grafiti{
  svg{
    opacity: 0;
    transition: opacity 1s ease-in-out;
  }
  &.active{
    svg{
      opacity: 1;
    }
  }
}
</style>
