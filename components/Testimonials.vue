<template>
  <section class="testimonials">
    <div class="container">
      <div class="sqrs">
        <span class="sqrs-left"></span>
        <span class="sqrs-right"></span>
        <span class="sqrs-left"></span>
      </div>
      <h2>What have past attendees said?</h2>
      <div class="testimonials-wrap">
        <div class="testimonials-item" v-for="(item, i) in items">
          <div class="row">
            <div class="left"><img :src="require(`@/assets/img/barcelona/testimonial-${++i}.png`)"></div>
            <div class="right">
              <h4 v-html="item.name"></h4>
              <svg width="194" height="34" viewBox="0 0 194 34" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M17.3706 0.959229L22.5237 12.1173L34.7412 13.5641L25.7085 21.907L28.1062 33.9592L17.3706 27.9573L6.63498 33.9592L9.03272 21.907L0 13.5641L12.2175 12.1173L17.3706 0.959229Z" fill="#FF3D00"/>
                <path d="M96.9995 0.959229L102.153 12.1173L114.37 13.5641L105.337 21.907L107.735 33.9592L96.9995 27.9573L86.2639 33.9592L88.6616 21.907L79.6289 13.5641L91.8464 12.1173L96.9995 0.959229Z" fill="#FF3D00"/>
                <path d="M57.1851 0.959229L62.3382 12.1173L74.5557 13.5641L65.523 21.907L67.9207 33.9592L57.1851 27.9573L46.4494 33.9592L48.8472 21.907L39.8145 13.5641L52.032 12.1173L57.1851 0.959229Z" fill="#FF3D00"/>
                <path d="M136.815 0.959229L141.968 12.1173L154.186 13.5641L145.153 21.907L147.551 33.9592L136.815 27.9573L126.079 33.9592L128.477 21.907L119.444 13.5641L131.662 12.1173L136.815 0.959229Z" fill="#FF3D00"/>
                <path d="M176.629 0.959229L181.783 12.1173L194 13.5641L184.967 21.907L187.365 33.9592L176.629 27.9573L165.894 33.9592L168.292 21.907L159.259 13.5641L171.476 12.1173L176.629 0.959229Z" fill="#FF3D00"/>
              </svg>
            </div>
          </div>
          <p v-html="item.text"></p>
          <svg v-if="i < 7" width="19" height="18" viewBox="0 0 19 18" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M17.9607 1.33276C17.9926 1.15738 17.9288 0.978263 17.7931 0.862629C17.6574 0.746995 17.4704 0.712339 17.3023 0.771669L1.36484 6.39667C1.18487 6.46019 1.05675 6.62062 1.03462 6.81019C1.01249 6.99976 1.10021 7.18539 1.26071 7.28865L4.90357 9.6324C5.05378 9.72904 5.24412 9.73822 5.40293 9.65648L11.1868 6.67947L7.53399 10.7531C7.46405 10.8311 7.42038 10.9291 7.40914 11.0333L6.95378 15.252C6.93177 15.4559 7.03649 15.6525 7.21795 15.7481C7.3994 15.8436 7.6208 15.8187 7.77644 15.6852L10.2099 13.5976L14.4443 16.6488C14.5835 16.7491 14.7644 16.771 14.9235 16.7069C15.0826 16.6428 15.1978 16.5015 15.2285 16.3328L17.9607 1.33276Z" stroke="#FF3D00" stroke-linejoin="round"/></svg>
          <svg v-else width="11" height="18" viewBox="0 0 11 18" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M3.35262 16.2432V16.7432H3.85262H6.6768H7.1768V16.2432V10.2161H8.91271H9.33326L9.40531 9.80176L9.87603 7.095L9.97788 6.50933H9.38343H7.29447V5.24427C7.29447 4.96614 7.36464 4.74865 7.4918 4.6056C7.60885 4.47391 7.83921 4.33212 8.32431 4.33212H9.50111H10.0011V3.83212V1.47852V1.07744L9.60957 0.99043L9.50111 1.47852C9.60957 0.99043 9.60952 0.990418 9.60946 0.990405L9.60932 0.990374L9.60897 0.990297L9.60799 0.990079L9.60486 0.989393L9.59408 0.987056L9.55507 0.97883C9.52158 0.971883 9.4734 0.962156 9.41263 0.950579C9.29118 0.927446 9.11885 0.896822 8.91243 0.866242C8.50203 0.805441 7.94602 0.743164 7.38287 0.743164C6.22184 0.743164 5.20111 1.09986 4.4699 1.83109C3.73802 2.56299 3.35262 3.61363 3.35262 4.8911V6.50933H1.49902H0.999023V7.00933V9.7161V10.2161H1.49902H3.35262V16.2432Z" stroke="#FF3D00"/></svg>
        </div>
      </div>
    </div>
    <div class="grafiti">
      <svg class="testimonials-grafiti" width="1047" height="549" viewBox="0 0 1047 549" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M682.574 180.039L714.567 211.028C726.836 202.337 738.44 193.071 749.349 183.293C757.062 190.545 765.181 197.524 773.705 204.208L807.541 174.587C798.109 167.199 789.257 159.396 780.974 151.209C803.728 125.034 821.992 96.2037 835.025 65.5829L788.591 52.0234C778.995 74.5533 766.185 95.9879 750.536 115.871C746.752 110.659 743.17 105.342 739.792 99.9134L696.022 118.59C702.876 129.615 710.493 140.248 718.785 150.474C707.597 160.995 695.51 170.885 682.574 180.039Z" fill="#FF3D00"/>
        <path d="M1005.46 199.347C939.111 285.877 897.697 384.591 884.664 486.615C865.724 458.92 853.435 426.165 848.695 390.275L847.845 383.871C842.275 341.866 837.004 302.195 841.705 262.835C843.308 249.428 834.156 237.195 818.932 232.39C803.68 227.585 786.988 231.687 777.393 242.6C770.085 250.915 763.211 259.581 756.772 268.568C725.321 260.125 690.49 252.474 652.967 245.774L642.599 285.637C651.19 287.172 659.628 288.755 667.901 290.386C662.476 305.073 653.932 317.889 646.595 327.179C635.976 340.611 625.164 350.221 620.801 353.738C613.435 351.076 605.886 348.765 598.211 346.831C628.572 284.806 651.77 220.446 667.495 154.399C670.922 139.984 663.393 125.665 648.314 117.902C633.244 110.155 614.429 110.914 600.364 119.845C588.278 127.52 576.162 135.979 564.037 145.165C565.543 140.256 566.315 135.251 566.286 130.222C566.171 106.637 549.47 84.1793 517.989 65.2711C452.122 25.6879 367.431 10.5054 285.722 0L278.163 40.2948C288.223 41.5899 298.33 42.9571 308.418 44.4362C292.654 88.0568 285.799 134.931 288.377 181.39C253.933 157.645 211.071 140.6 157.464 129.327C150.542 127.872 143.389 126.497 136.467 125.162C107.439 119.581 77.4253 113.801 56.1873 100.833C52.432 98.5383 49.7193 95.5002 49.2946 93.0857C48.5995 89.2081 53.7739 83.5796 60.3673 81.0372C68.8336 77.7673 80.3118 77.1596 96.4913 79.1184C137.278 84.0593 175.796 99.8974 205.22 123.786C205.887 124.346 206.562 124.898 207.238 125.449L241.856 96.4596C241.258 95.9559 240.649 95.4602 240.051 94.9725C216.322 74.9291 206.138 43.6287 214.691 16.4777L167.04 6.18013C162.242 21.4346 161.248 37.3046 163.719 52.7829C144.528 46.0352 124.303 41.2861 103.616 38.7757C87.1755 36.785 62.6456 35.162 39.554 44.0844C12.6782 54.4619 -3.34683 77.0717 0.591862 99.0739C2.98597 112.442 12.35 124.722 26.9657 133.644C56.3803 151.617 93.016 158.661 125.327 164.881C132.316 166.224 138.919 167.495 145.348 168.846C193.443 178.96 229.528 193.351 258.924 214.154C260.198 215.057 261.463 215.969 262.708 216.896C276.715 227.25 285.201 236.308 289.42 245.398C294.758 256.911 292.354 271.494 277.42 277.09C267.062 280.976 252.871 280.808 238.497 276.635C222.78 272.07 208.03 263.563 194.254 255.24C149.335 228.089 106.956 197.532 68.293 164.433L30.8657 190.792C67.1635 231.119 104.687 272.813 129.15 318.656L174.184 302.171C171.848 297.797 169.415 293.464 166.895 289.179C182.544 298.597 200.925 308.934 222.211 315.115C235.012 318.832 247.87 320.687 260.227 320.687C273.53 320.687 286.263 318.536 297.731 314.235C305.232 311.421 311.864 307.695 317.56 303.29C324.887 320.135 333.489 336.493 343.326 352.139L386.999 333.311C366.996 301.491 352.941 266.897 344.986 231.271L413.73 218.423C419.522 217.344 425.362 216.328 431.541 215.249C454.874 211.188 478.911 206.99 501.617 199.043C498.315 202.249 495.004 205.487 491.712 208.797C480.687 219.87 469.953 231.311 459.633 242.96C445.355 239.57 430.266 236.26 414.28 233.006L402.522 272.597C411.992 274.524 421.144 276.483 429.987 278.466C422.013 288.627 414.434 298.821 407.358 308.95L449.97 329.37C458.388 317.313 468.263 304.241 479.326 290.674C510.691 299.284 537.103 308.423 558.95 318.217C539.14 360.398 515.914 401.484 489.356 441.251L532.441 460.983C549.122 436.007 564.529 410.527 578.662 384.607C608.483 391.195 636.063 405.146 656.693 424.142L693.3 396.871C684.544 388.812 674.832 381.441 664.368 374.877C669.735 369.88 677.062 362.541 684.669 353.347C695.375 340.411 707.886 322.182 715.522 300.74C721.759 302.235 727.869 303.762 733.855 305.313C724.471 322.766 716.517 341.186 710.049 360.478C696.978 399.47 689.612 443.098 688.164 490.157L737.378 491.188C739.657 416.995 757.564 353.475 790.715 301.739C791.265 330.937 795.107 359.95 798.872 388.317L799.721 394.697C807.049 450.198 830.382 499.711 867.201 537.887C874.122 545.058 884.297 549 894.897 549C898.536 549 902.224 548.536 905.854 547.577C920.064 543.827 929.785 533.434 930.635 521.105C937.952 414.652 978.189 310.941 1047 221.181L1005.46 199.347ZM421.424 175.338C415.342 176.393 409.048 177.489 402.898 178.64L338.615 190.649C334.328 144.03 340.294 96.7794 356.889 52.591C405.457 62.0811 451.63 75.7605 489.096 98.2664C499.512 104.527 516.995 117.023 517.062 130.382C517.12 142.487 502.563 153.672 488.102 159.388C468.505 167.143 444.573 171.317 421.424 175.338ZM509.378 256.04C540.058 222.708 576.432 189.074 615.327 162.17C605.056 202.017 591.936 241.201 576.056 279.561C556.604 271.198 534.555 263.411 509.378 256.04Z" fill="#FF3D00"/>
      </svg>
    </div>
  </section>
</template>
<script>
export default{
  data(){
    return{
      items: [
        {
          name: `Nick<br>Fisher`,
          text: `Here, the music is great. The tactics are fresh, and I truly believe that anyone who wants to stay up to date in your current tactics and environment should be here.`
        },
        {
          name: `Hannah<br>McGough`,
          text: `I’m here to meet other co-entrepreneurs who like to talk shop and also have a great character, and I’m just here helping other creatives.`
        },
        {
          name: `Omeed<br>Tabiei`,
          text: `There’s no other place for eCom founders and winners to meet so, I’m here to show up with the winners.`
        },
        {
          name: `Liam<br>Dean`,
          text: `I’m just here to connect with high level upgrades, and everyone I’ve met is mindblowing.`
        },
        {
          name: `Joe<br>Marston`,
          text: `SecondGeekOut. I was in Dubai as well. Having a really good time and so many good people here. Everyone here is pretty high level. I’m having a good time.`
        },
        {
          name: `Adam<br>Davis`,
          text: `I went to the very first GeekOut and I got tremendous value from that event. Four years later, I’m back. I’m here to learn It’s very personable and it’s not a pitch-fest. I haven’t been pitched once since being here. People just kinda open up their businesses. They’re actually really transparent.`
        },
        {
          name: `Zach<br>Nyborg`,
          text: `It’s a true “No Douchebag” environment where people open up their playbooks. They take some approach and they’re helping each other out.`
        },
        {
          name: `Cameron<br>Wethington`,
          text: `"I came over to GeekOut to learn more about growth, more about Tiktok, Facebook, Facebook Ads, as well as client retention,...we want to know the in's and out's we can never stop learning, it's like bamboo if you're not growing you're dying."`
        },
        {
          name: `Aaron<br>Ball`,
          text: `I’m having a good time network and taking as much as value as I can. Come to GeekOut and just get good vibes.`
        },
        {
          name: `Damien<br>Watts`,
          text: `I’m here at GeekOut event to learn more about creatives: how to build creatives across multiple platforms, the content, the scripting, the pre and post productions. That’s what we’re looking for. So, if you’re looking any kind of information around: influence marketing, TikTok, and everything that’s happening in the eCommerce space. GeekOut is the event to come to.`
        }
      ]
    }
  }
}
</script>
<style lang="scss" scoped>
.testimonials{
  position: relative;
  padding: 80px 0 0;
  @media(min-width:1200px){
    padding: 160px 0;
  }
  .sqrs{
    @media(min-width:992px){
      margin-left: 50%;
    }
  }
  .container{
    position: relative;
    z-index: 2;
  }
  &-grafiti{
    position: absolute;
    z-index: 1;
    right: 0;
    transform: translate(0, 0);
    width: 100%;
    height: auto;
    left: 50%;
    @media(max-width:991px){
      top: 100%;
      left: 0;
      transform: translate(0, -30px);
      path{
        fill: #1D1D1D;
      }
    }
    @media(min-width:992px){
      width: 50%;
      bottom: 0;
    }
    @media(min-width:1920px){
      width: 1047px;
    }
  }
  &-wrap{
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    margin-left: -15px;
    margin-right: -15px;
  }
  &-item{
    flex: 1 100%;
    max-width: 100%;
    padding: 25px 15px;
    @media(min-width:576px){
      flex: 1 50%;
      max-width: 50%;
    }
    @media(min-width:992px){
      flex: 1 33.333%;
      max-width: 33.333%;
    }
  }
  h2{
    font-weight: 700;
    font-size: 42px;
    line-height: 1;
    text-transform: uppercase;
    color: #FFFFFF;
    margin-bottom: 15px;
    padding-left: 30px;
    max-width: 410px;
    width: 100%;
    @media(min-width:992px){
      font-size: 45px;
      padding-left: 60px;
      font-size: 70px;
      line-height: 66px;
      margin-bottom: 60px;
      margin-left: 50%;
    }
  }
  svg{
    max-width: 100%;
    height: auto;
  }
  h4{
    font-weight: 700;
    font-size: 25px;
    line-height: 1.2;
    color: #FFFFFF;
    margin-bottom: 5px;
    @media(min-width:768px){
      font-size: 30px;
      line-height: 34px;
      margin-bottom: 15px;
    }
  }
  p{
    margin: 0;
    font-weight: 400;
    font-size: 18px;
    line-height: 21px;
    color: #FFFFFF;
    padding: 40px 0 25px;
    @media(min-width:768px){
      padding: 30px 0 25px;
    }
  }
  .row{
    display: flex;
    justify-content: flex-start;
    .left{
      margin-right: 30px;
    }
  }
}
</style>