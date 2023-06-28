<template>
  <section class="topics">
    <div class="container">
      <div class="sqrs">
        <span class="sqrs-left"></span>
        <span class="sqrs-right"></span>
        <span class="sqrs-left"></span>
      </div>
      <h2>Topics</h2>
      <div class="slider">
        <div class="slider-item" v-for="(slide, i) in slides" :class="(currentSlide === i + 1) ? 'active':'' ">
          <div class="slider-left">
            <img :src="require(`@/assets/img/barcelona/slider-${++i}.png`)">
          </div>
          <div class="slider-right">
            <h3 v-html="slide.title"></h3>
            <h4 v-html="slide.text"></h4>
          </div>
        </div>
      </div>
      <div class="slider-nav">
        <button @click.prevent="prev">
          <svg width="16" height="15" viewBox="0 0 16 15" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M3.828 9.22061L9.192 14.3929L7.778 15.7563L0 8.25635L7.778 0.756348L9.192 2.11981L3.828 7.29209L16 7.29209V9.22061L3.828 9.22061Z" fill="white"/>
          </svg>
        </button>
        <div class="slider-pagin"><span>{{ currentSlide }}</span>/{{ slides.length }}</div>
        <button @click.prevent="next">
          <svg width="16" height="15" viewBox="0 0 16 15" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M12.8575 8.46426L7.49355 13.6365L8.90755 15L16.6855 7.5L8.90755 0L7.49355 1.36346L12.8575 6.53574L0.685547 6.53574V8.46426L12.8575 8.46426Z" fill="white"/>
          </svg>
        </button>
      </div>
    </div>
    <div class="grafiti">
      <svg class="topics-grafiti" width="1047" height="549" viewBox="0 0 1047 549" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M682.574 180.039L714.567 211.028C726.836 202.337 738.44 193.071 749.349 183.293C757.062 190.545 765.181 197.524 773.705 204.208L807.541 174.587C798.109 167.199 789.257 159.396 780.974 151.209C803.728 125.034 821.992 96.2037 835.025 65.5829L788.591 52.0234C778.995 74.5533 766.185 95.9879 750.536 115.871C746.752 110.659 743.17 105.342 739.792 99.9134L696.022 118.59C702.876 129.615 710.493 140.248 718.785 150.474C707.597 160.995 695.51 170.885 682.574 180.039Z" fill="#1D1D1D"/><path d="M1005.46 199.347C939.111 285.877 897.697 384.591 884.664 486.615C865.724 458.92 853.435 426.165 848.695 390.275L847.845 383.871C842.275 341.866 837.004 302.195 841.705 262.835C843.308 249.428 834.156 237.195 818.932 232.39C803.68 227.585 786.988 231.687 777.393 242.6C770.085 250.915 763.211 259.581 756.772 268.568C725.321 260.125 690.49 252.474 652.967 245.774L642.599 285.637C651.19 287.172 659.628 288.755 667.901 290.386C662.476 305.073 653.932 317.889 646.595 327.179C635.976 340.611 625.164 350.221 620.801 353.738C613.435 351.076 605.886 348.765 598.211 346.831C628.572 284.806 651.77 220.446 667.495 154.399C670.922 139.984 663.393 125.665 648.314 117.902C633.244 110.155 614.429 110.914 600.364 119.845C588.278 127.52 576.162 135.979 564.037 145.165C565.543 140.256 566.315 135.251 566.286 130.222C566.171 106.637 549.47 84.1793 517.989 65.2711C452.122 25.6879 367.431 10.5054 285.722 0L278.163 40.2948C288.223 41.5899 298.33 42.9571 308.418 44.4362C292.654 88.0568 285.799 134.931 288.377 181.39C253.933 157.645 211.071 140.6 157.464 129.327C150.542 127.872 143.389 126.497 136.467 125.162C107.439 119.581 77.4253 113.801 56.1873 100.833C52.432 98.5383 49.7193 95.5002 49.2946 93.0857C48.5995 89.2081 53.7739 83.5796 60.3673 81.0372C68.8336 77.7673 80.3118 77.1596 96.4913 79.1184C137.278 84.0593 175.796 99.8974 205.22 123.786C205.887 124.346 206.562 124.898 207.238 125.449L241.856 96.4596C241.258 95.9559 240.649 95.4602 240.051 94.9725C216.322 74.9291 206.138 43.6287 214.691 16.4777L167.04 6.18013C162.242 21.4346 161.248 37.3046 163.719 52.7829C144.528 46.0352 124.303 41.2861 103.616 38.7757C87.1755 36.785 62.6456 35.162 39.554 44.0844C12.6782 54.4619 -3.34683 77.0717 0.591862 99.0739C2.98597 112.442 12.35 124.722 26.9657 133.644C56.3803 151.617 93.016 158.661 125.327 164.881C132.316 166.224 138.919 167.495 145.348 168.846C193.443 178.96 229.528 193.351 258.924 214.154C260.198 215.057 261.463 215.969 262.708 216.896C276.715 227.25 285.201 236.308 289.42 245.398C294.758 256.911 292.354 271.494 277.42 277.09C267.062 280.976 252.871 280.808 238.497 276.635C222.78 272.07 208.03 263.563 194.254 255.24C149.335 228.089 106.956 197.532 68.293 164.433L30.8657 190.792C67.1635 231.119 104.687 272.813 129.15 318.656L174.184 302.171C171.848 297.797 169.415 293.464 166.895 289.179C182.544 298.597 200.925 308.934 222.211 315.115C235.012 318.832 247.87 320.687 260.227 320.687C273.53 320.687 286.263 318.536 297.731 314.235C305.232 311.421 311.864 307.695 317.56 303.29C324.887 320.135 333.489 336.493 343.326 352.139L386.999 333.311C366.996 301.491 352.941 266.897 344.986 231.271L413.73 218.423C419.522 217.344 425.362 216.328 431.541 215.249C454.874 211.188 478.911 206.99 501.617 199.043C498.315 202.249 495.004 205.487 491.712 208.797C480.687 219.87 469.953 231.311 459.633 242.96C445.355 239.57 430.266 236.26 414.28 233.006L402.522 272.597C411.992 274.524 421.144 276.483 429.987 278.466C422.013 288.627 414.434 298.821 407.358 308.95L449.97 329.37C458.388 317.313 468.263 304.241 479.326 290.674C510.691 299.284 537.103 308.423 558.95 318.217C539.14 360.398 515.914 401.484 489.356 441.251L532.441 460.983C549.122 436.007 564.529 410.527 578.662 384.607C608.483 391.195 636.063 405.146 656.693 424.142L693.3 396.871C684.544 388.812 674.832 381.441 664.368 374.877C669.735 369.88 677.062 362.541 684.669 353.347C695.375 340.411 707.886 322.182 715.522 300.74C721.759 302.235 727.869 303.762 733.855 305.313C724.471 322.766 716.517 341.186 710.049 360.478C696.978 399.47 689.612 443.098 688.164 490.157L737.378 491.188C739.657 416.995 757.564 353.475 790.715 301.739C791.265 330.937 795.107 359.95 798.872 388.317L799.721 394.697C807.049 450.198 830.382 499.711 867.201 537.887C874.122 545.058 884.297 549 894.897 549C898.536 549 902.224 548.536 905.854 547.577C920.064 543.827 929.785 533.434 930.635 521.105C937.952 414.652 978.189 310.941 1047 221.181L1005.46 199.347ZM421.424 175.338C415.342 176.393 409.048 177.489 402.898 178.64L338.615 190.649C334.328 144.03 340.294 96.7794 356.889 52.591C405.457 62.0811 451.63 75.7605 489.096 98.2664C499.512 104.527 516.995 117.023 517.062 130.382C517.12 142.487 502.563 153.672 488.102 159.388C468.505 167.143 444.573 171.317 421.424 175.338ZM509.378 256.04C540.058 222.708 576.432 189.074 615.327 162.17C605.056 202.017 591.936 241.201 576.056 279.561C556.604 271.198 534.555 263.411 509.378 256.04Z" fill="#1D1D1D"/></svg>
    </div>
  </section>
</template>
<script>
export default{
  data(){
    return {
      currentSlide: 1,
      slides: [
        {
          title: 'Rabah Rahil <br>(Triple Whale) ',
          text: 'Data Drop / Metrics That Matter'
        },
        {
          title: 'Tyler Stephens & Cody <br> Iverson (Viscap) ',
          text: `Take Control of Your Creatives! 5x your Content’s ROI with Creative CRO!`
        },
        {
          title: 'Zach Johnson <br> (Dash.fi)',
          text: 'True Life: Points Are A Terrible Inflation Hedge '
        },
        {
          title: 'Jem <br> Bourough',
          text: `$310M Ad Spend Secrets Behind Google Ads`
        },
        {
          title: 'Neil Forrest <br> (Gorgias)',
          text: 'What Brands Need To Think About In Building Community'
        },
        {
          title: 'Raoul <br> Van Heerden',
          text: 'Growth Marketing - Facebook in 2022 & beyond'
        },
        {
          title: 'Daniel <br> James',
          text: 'Growth Marketing - Facebook in 2022 & Beyond'
        },
        {
          title: 'Aaron <br> Nosbisch',
          text: 'The Conscious Compound™ Revolution: Cannabis, Adaptogens, and Psychedelics in Ecomm'
        },
        {
          title: 'Joshua <br> Chin',
          text: 'Surviving Ad-mageddon with Email & SMS Marketing'
        },
        {
          title: 'Lauren <br> Tickner',
          text: 'Building Remote Operations'
        },
        {
          title: 'Noah Tucker & <br> Jordan Rolband',
          text: 'Two Ways To Do Affiliate Marketing'
        },
        {
          title: 'Marc <br> Weindinger',
          text: 'What all of our 400k spend per month Meta Ad Accounts have in common!'
        },
        {
          title: 'Jack Pierse <br> (Wayflyer) ',
          text: 'How My TikTok House Turned into $120M of Financing?'
        }
      ]
    }
  },
  methods: {
    setHeight(){
      setTimeout(()=>{
        document.querySelector('.slider').style.minHeight = document.querySelector('.slider-item.active').clientHeight + 'px'
      }, 500)
    },
    prev(){
      this.currentSlide = (this.currentSlide === 1) ? this.slides.length : this.currentSlide - 1
      this.setHeight()
    },
    next(){
      this.currentSlide = (this.currentSlide === this.slides.length) ? 1 : this.currentSlide + 1
      this.setHeight()
    }
  },
  mounted(){
    this.setHeight()
  }
}
</script>
<style lang="scss" scoped>
.topics{
  padding: 80px 0 0;
  @media(min-width:1200px){
    padding: 160px 0 0;
  }
  .sqrs{
    @media(min-width:992px){
      margin-left: 50%;
    }
  }
  &-grafiti{
    position: absolute;
    bottom: 0;
    z-index: 1;
    width: 100%;
    height: auto;
    left: 50%;
    transform: translate(0, 80%);
    display: none;
    @media(min-width:768px){
      display: block;
      width: 50%;
      transform: translate(0, 50%);
    }
    @media(min-width:1920px){
      width: 1047px;
    }
  }
  .container{
    position: relative;
  }
  h2{
    font-weight: 700;
    font-size: 45px;
    line-height: 1;
    text-transform: uppercase;
    color: #FFFFFF;
    margin-bottom: 40px;
    padding-left: 30px;
    @media(min-width:992px){
      padding-left: 60px;
      font-size: 70px;
      line-height: 66px;
      margin-bottom: 60px;
      margin-left: 50%;
    }
  }
}
.slider{
  position: relative;
  width: 100%;
  background: none;
  min-height: 488px;
  @media(min-width:1200px){
    min-height: 475px;
  }
  &-item{
    display: flex;
    flex-wrap: wrap;
    align-items: center;
    position: absolute;
    left: 0;
    width: 100%;
    top: 0;
    &.active{
      z-index: 2;
      img{
        opacity: 1;
        transform: translate(0, 0) scale(1);
        transition: 1s ease-in-out;
      }
      h3, h4{
        opacity: 1;
        transform: translate(0, 0);
        transition: 1s ease-in-out;
      }
      h4{
        transition-delay: .1s;
      }
      h4{
        transition-delay: .2s;
      }
    }
  }
  &-left, &-right{
    flex: 1 100%;
    @media(max-width:575px){
      text-align: center;
    }
    @media(min-width:576px){
      flex: 1 50%;
    }
  }
  &-left{
    margin-bottom: 40px;
    padding: 0 15px;
    @media(min-width:768px){
      margin-bottom: 0;
      padding: 0;
    }
    img{
      @media(max-width:575px){
        margin: 0 auto;
      }
      width: 315px;
      height: 315px;
      @media(min-width:992px){
        width: 482px;
        height: 482px;
      }
    }
    @media(min-width:1200px){
      padding-right: 120px;
    }
  }
  &-right{
    position: relative;
    padding-left: 0;
    @media(min-width:576px){
      padding-left: 30px;
    }
    @media(min-width:1200px){
      padding-left: 45px;
    }
  }
  &-pagin{
    font-weight: 500;
    font-size: 18px;
    line-height: 130%;
    letter-spacing: 0.08em;
    span{
      color: #FF3D00;
    }
  }
  &-nav{
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 100%;
    position: relative;
    width: 250px;
    margin: 30px auto 0;
    @media(min-width:992px){
      margin: 0;
      left: calc(50% + 30px);
      bottom: 0;
      position: absolute;
      z-index: 3;
    }
    @media(min-width:1200px){
      left: calc(50% + 45px);
    }
    button{
      background: none;
      border: none;
      &:hover{
        opacity: .5;
      }
      &:active{
        opacity: 1;
      }
    }
  }
  h3{
    font-weight: 400;
    line-height: 126.5%;
    text-transform: uppercase;
    color: #FF3D00;
    margin-bottom: 30px;
    font-size: 25px;
    opacity: 0;
    transform: translate(0, 50px);
    transition: .5s ease-in-out;
    @media(min-width:576px){
      padding-top: 0;
    }
    @media(min-width:768px){
      font-size: 30px;
    }
    b{
      display: block;
    }
  }
  h4{
    font-weight: 400;
    line-height: 126.5%;
    color: #FFFFFF;
    font-size: 18px;
    opacity: 0;
    transform: translate(0, 50px);
    transition: .5s ease-in-out;
  }
  img{
    display: block;
    opacity: 0;
    transform: translate(-200px, 0) scale(.5);
    transition: .5s ease-in-out;
  }
}
</style>