<template>
  <section class="experience">
    <div class="container">
      <div class="sqrs">
        <span class="sqrs-left"></span>
        <span class="sqrs-right"></span>
        <span class="sqrs-left"></span>
      </div>
      <h2>What is the GeekOut Experience Like</h2>
      <h4>#Insane #Unique<br> #Connecting<br> #Wild #Fun</h4>
      <div class="experience-video" ref="video">
          <svg v-if="vimeoObjParams.play" @click.prevent="play" class="video-btn" width="60" height="60" viewBox="0 0 60 60" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path class="pause" fill-rule="evenodd" clip-rule="evenodd" d="M0 10C0 4.47715 4.47715 0 10 0H50C55.5228 0 60 4.47715 60 10V50C60 55.5228 55.5228 60 50 60H10C4.47715 60 0 55.5228 0 50V10ZM27 21H22V39H27V21ZM38 21H33V39H38V21Z" fill="white"/>
          </svg>
          <svg class="video-start" v-else @click.prevent="play" width="100" height="100" viewBox="0 0 100 100" fill="none" xmlns="http://www.w3.org/2000/svg"> <path class="path-hover" d="M36 28V32H32V36H28V63H32V67H36V71H64V67H68V63H72V36H68V32H64V28H36Z" fill="#FF3D00"/> <path d="M56 48H54V50H56V48Z" fill="white"/> <path d="M54 48H52V50H54V48Z" fill="white"/> <path d="M54 46H52V48H54V46Z" fill="white"/> <path d="M54 50H52V52H54V50Z" fill="white"/> <path d="M52 48H50V50H52V48Z" fill="white"/> <path d="M52 44H50V46H52V44Z" fill="white"/> <path d="M52 46H50V48H52V46Z" fill="white"/> <path d="M52 50H50V52H52V50Z" fill="white"/> <path d="M52 52H50V54H52V52Z" fill="white"/> <path d="M50 48H48V50H50V48Z" fill="white"/> <path d="M50 54H48V56H50V54Z" fill="white"/> <path d="M50 42H48V44H50V42Z" fill="white"/> <path d="M50 44H48V46H50V44Z" fill="white"/> <path d="M50 46H48V48H50V46Z" fill="white"/> <path d="M50 50H48V52H50V50Z" fill="white"/> <path d="M50 52H48V54H50V52Z" fill="white"/> <path d="M48 48H46V50H48V48Z" fill="white"/> <path d="M48 40H46V42H48V40Z" fill="white"/> <path d="M48 42H46V44H48V42Z" fill="white"/> <path d="M48 44H46V46H48V44Z" fill="white"/> <path d="M48 46H46V48H48V46Z" fill="white"/> <path d="M48 50H46V52H48V50Z" fill="white"/> <path d="M48 54H46V56H48V54Z" fill="white"/> <path d="M48 52H46V54H48V52Z" fill="white"/> <path d="M48 56H46V58H48V56Z" fill="white"/> <g class="text"> <path d="M93.6827 25.489C88.9725 27.1348 87.3614 27.7323 86.3476 28.2274C87.1338 27.4896 88.3572 26.1548 91.6062 22.4193L90.6711 21.0368C85.7937 22.7639 84.2662 23.3208 83.2162 23.8562C84.0097 23.1293 85.1787 21.8313 88.5799 17.9454L87.6742 16.6065L81.3794 23.9558L82.344 25.3818C87.2473 23.7165 88.7021 23.193 89.6394 22.702C88.8564 23.3742 87.7922 24.522 84.391 28.408L85.3777 29.8666L94.5516 26.7735L93.6827 25.489Z" fill="white"/> <path d="M94.0847 36.9766L92.6618 32.7689L96.4347 31.4936L95.9422 30.0371L87.1013 33.0253L87.5938 34.4818L91.3668 33.2066L92.7897 37.4143L89.0167 38.6895L89.5093 40.146L98.3501 37.1578L97.8576 35.7013L94.0847 36.9766Z" fill="white"/> <path d="M90.734 49.8106L99.7081 45.5723L99.544 43.8323L89.9381 41.372L90.0874 42.9551L92.3967 43.5029L92.7434 47.1793C92.097 47.4646 91.3889 47.7953 90.5785 48.1621L90.734 49.8106ZM93.7055 43.8019C97.1891 44.6219 97.9785 44.7322 98.6664 44.7466C97.9921 44.8761 97.2516 45.1439 93.9721 46.6278L93.7055 43.8019Z" fill="white"/> <path d="M90.2559 55.0292L98.1409 55.9551L97.8465 58.4609L99.2303 58.6234L100 52.0717L98.6162 51.9092L98.3203 54.4281L90.4353 53.5022L90.2559 55.0292Z" fill="white"/> <path d="M88.2588 63.1241C87.8278 64.4487 87.9847 65.4533 88.188 65.9754L89.6255 66.4429C89.4018 65.9833 89.1205 65.0212 89.5393 63.734C90.1045 61.997 91.9265 61.028 93.7889 61.6338C95.6513 62.2395 96.5584 64.0822 95.9891 65.8317C95.5703 67.1188 94.7891 67.7353 94.3253 67.9714L95.7627 68.4389C96.2344 68.1363 96.9525 67.4163 97.3835 66.0917C98.1927 63.6049 96.827 61.005 94.2646 60.1717C91.7022 59.3383 89.068 60.6373 88.2588 63.1241Z" fill="white"/> <path d="M88.4974 75.1079L90.7763 71.2951L94.1952 73.3375L94.984 72.0177L86.9729 67.2318L86.184 68.5516L89.6029 70.594L87.324 74.4068L83.9051 72.3644L83.1163 73.6842L91.1274 78.4701L91.9163 77.1503L88.4974 75.1079Z" fill="white"/> <path d="M80.795 89.3285C78.4855 83.4979 77.9219 82.1974 77.4632 81.4826C78.1013 82.0432 79.3042 82.7769 84.7421 85.9362L86.008 84.8482L77.3626 79.9747L76.0369 81.114L79.579 90.3736L80.795 89.3285Z" fill="white"/> <path d="M70.8319 84.8236L75.669 92.8026L76.9842 92.0057L72.147 84.0267L70.8319 84.8236Z" fill="white"/> <path d="M65.8645 87.3678C63.1651 88.4405 62.3102 90.9863 63.2763 93.4164C64.2425 95.8465 66.6123 97.1108 69.3118 96.038L72.1944 94.8925L68.7472 86.2222L65.8645 87.3678ZM70.2506 94.166L68.7971 94.7436C67.0748 95.428 65.4604 94.7827 64.6933 92.8533C63.9261 90.9239 64.6569 89.3466 66.3792 88.6622L67.8327 88.0846L70.2506 94.166Z" fill="white"/> <path d="M55.6755 99.662L61.4043 98.6957L59.8517 89.4956L54.1229 90.4619L54.3547 91.8354L58.5671 91.1249L59.0088 93.7424L55.5871 94.3196L55.8123 95.6542L59.234 95.0771L59.6561 97.5779L55.4437 98.2885L55.6755 99.662Z" fill="white"/> <path d="M48.1018 90.4144C45.3856 90.2546 43.2445 92.1823 43.0832 94.924C42.9219 97.6657 44.8222 99.831 47.5384 99.9908C50.2546 100.15 52.3826 98.2221 52.5439 95.4804C52.7052 92.7386 50.818 90.5741 48.1018 90.4144ZM48.0169 91.8574C49.8671 91.9662 51.1175 93.5404 51.0086 95.3901C50.8998 97.2398 49.4734 98.6565 47.6233 98.5477C45.76 98.4382 44.5096 96.864 44.6184 95.0143C44.7272 93.1646 46.1536 91.7478 48.0169 91.8574Z" fill="white"/> <path d="M3.67907 69.219C8.55059 68.1402 10.2209 67.7369 11.2861 67.3648C10.4183 68.0048 9.04597 69.1859 5.37883 72.5122L6.14432 73.9953C11.1914 72.8555 12.774 72.4827 13.8799 72.0748C13.006 72.7031 11.6921 73.8541 7.85614 77.3118L8.59752 78.7482L15.7155 72.1925L14.9259 70.6627C9.86036 71.7381 8.35394 72.0864 7.36523 72.4634C8.22209 71.8882 9.41432 70.8739 13.2503 67.4162L12.4426 65.8514L2.96782 67.841L3.67907 69.219Z" fill="white"/> <path d="M4.6424 57.8309L5.55788 62.1772L1.66063 62.9977L1.97752 64.5022L11.1097 62.5796L10.7928 61.0751L6.89555 61.8956L5.98007 57.5492L9.87732 56.7288L9.56042 55.2243L0.428257 57.1468L0.745153 58.6513L4.6424 57.8309Z" fill="white"/> <path d="M9.46283 45.3282L0.0455427 48.4612L0 50.2084L9.24196 53.8013L9.28339 52.2118L7.05634 51.3913L7.15257 47.6999C7.82852 47.4941 8.5712 47.2505 9.41968 46.9834L9.46283 45.3282ZM5.79274 50.9377C2.43245 49.7065 1.662 49.5024 0.980781 49.4058C1.66576 49.3579 2.43301 49.1807 5.8667 48.1002L5.79274 50.9377Z" fill="white"/> <path d="M10.5049 40.3751L2.78149 38.5373L3.36584 36.0828L2.01041 35.7602L0.482586 42.1778L1.83802 42.5003L2.42541 40.033L10.1488 41.8708L10.5049 40.3751Z" fill="white"/> <path d="M13.3815 32.6371C13.9665 31.3729 13.9298 30.3569 13.7898 29.8143L12.4179 29.1798C12.5855 29.6627 12.7508 30.6513 12.1823 31.8798C11.4152 33.5376 9.49119 34.2838 7.7137 33.4617C5.9362 32.6396 5.25402 30.7024 6.02668 29.0327C6.59514 27.8042 7.44388 27.2846 7.93243 27.1052L6.56054 26.4706C6.05632 26.7152 5.25797 27.345 4.67296 28.6093C3.57467 30.9826 4.62243 33.726 7.06797 34.8571C9.51352 35.9882 12.2832 35.0105 13.3815 32.6371Z" fill="white"/> <path d="M14.5486 20.65L11.8365 24.168L8.68197 21.7373L7.74316 22.9551L15.1349 28.6507L16.0737 27.433L12.9192 25.0023L15.6313 21.4843L18.7858 23.915L19.7247 22.6972L12.3329 17.0015L11.3941 18.2193L14.5486 20.65Z" fill="white"/> <path d="M23.8923 7.34549C25.4914 13.4094 25.8962 14.7678 26.2665 15.5321C25.6997 14.8995 24.5927 14.0279 19.5694 10.2441L18.1831 11.1737L26.1869 17.0412L27.6388 16.0677L25.2241 6.45248L23.8923 7.34549Z" fill="white"/> <path d="M33.1973 13.0003L29.3305 4.50879L27.9308 5.14584L31.7977 13.6374L33.1973 13.0003Z" fill="white"/> <path d="M38.3199 11.0663C41.1278 10.322 42.2793 7.89591 41.6089 5.3682C40.9385 2.84049 38.7359 1.30355 35.928 2.04788L32.9296 2.84274L35.3215 11.8612L38.3199 11.0663ZM34.7732 3.7951L36.2851 3.3943C38.0766 2.91941 39.6028 3.75197 40.1351 5.75889C40.6674 7.76582 39.7543 9.24504 37.9628 9.71993L36.4509 10.1207L34.7732 3.7951Z" fill="white"/> <path d="M50.1151 0L44.3117 0.270909L44.7469 9.59087L50.5504 9.31996L50.4854 7.92853L46.2182 8.12773L46.0943 5.47613L49.5606 5.31432L49.4975 3.96227L46.0312 4.12408L45.9129 1.59063L50.1801 1.39143L50.1151 0Z" fill="white"/> <path d="M56.5791 10.062C59.2566 10.5458 61.6133 8.88855 62.102 6.18588C62.5907 3.48322 60.9635 1.10592 58.286 0.622027C55.6086 0.138133 53.2648 1.79777 52.7761 4.50044C52.2874 7.2031 53.9017 9.57806 56.5791 10.062ZM56.8363 8.6395C55.0126 8.30989 53.9598 6.59727 54.2895 4.77394C54.6192 2.95061 56.2051 1.71487 58.0288 2.04448C59.8656 2.37643 60.9183 4.08905 60.5886 5.91238C60.259 7.73571 58.6731 8.97145 56.8363 8.6395Z" fill="white"/> </g> </svg>
        <div class="video-frame" :id="vimeoObjParams.id"></div>
      </div>
    </div>
  </section>
</template>
<script>
import Player from '@vimeo/player'
export default {
  data(){
    return {
      player: null,
      vimeoObjParams: {
        id: 'flashbackVideo',
        option: {
          id: 712849960,
          autoplay: true,
          responsive: true,
          muted: true,
          controls: false,
          loop: true,
        },
        play: false,
      }
    }
  },
  methods: {
    videoInit() {
      this.player = new Player(
        this.vimeoObjParams.id,
        this.vimeoObjParams.option
      ).on('ended', function () {})
    },
    play() {
      if(this.vimeoObjParams.play){
        this.player.pause()
        this.player.setMuted(true)
        this.vimeoObjParams.play = false
        this.$refs.video.classList.remove('video-active')
      } else {
        this.player = new Player(this.$el.querySelector('iframe'))
        this.player.play()
        this.player.setMuted(false)
        this.vimeoObjParams.play = true
        this.$refs.video.classList.add('video-active')
      }
    }
  },
  mounted(){
    this.videoInit()
  }
}
</script>
<style lang="scss" scoped>
.experience{
  padding: 80px 0 0;
  @media(min-width:768px){
    br{
      display: none;
    }
  }
  @media(min-width:1200px){
    padding: 160px 0 0;
  }
  .sqrs{
    @media(min-width:992px){
      margin-left: 50%;
    }
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
      max-width: 500px;
      width: 100%;
      padding-left: 60px;
      font-size: 70px;
      line-height: 66px;
      margin-bottom: 60px;
      margin-left: 50%;
    }
  }
  h4{
    font-weight: 500;
    font-size: 18px;
    line-height: 126.5%;
    color: #FF3D00;
    padding-left: 30px;
    margin-bottom: 40px;
    @media(min-width:992px){
      padding-left: 60px;
      margin-bottom: 60px;
      margin-left: 50%;
    }
  }
  &-video{
    max-width: 790px;
    margin: 0 auto;
    position: relative;
  }
}
.video{
  &-start{
    position: absolute;
    cursor: pointer;
    z-index: 4;
    right: 20px;
    bottom: 10px;
    width: 100px;
    height: auto;
    @media(min-width:768px){
      right: 80px;
      bottom: 30px;
    }
    path{
      transition: transform .25s ease;
      transform-origin: center center;
    }
    .path-hover{
      &:hover{
        transform: scale(1.2);
      }
    }
    .text{
      animation-name: spinFront;
      animation-duration: 10s;
      animation-iteration-count: infinite;
      animation-timing-function: ease-in-out;
      transform-origin: center center;
    }
  }
  &-btn{
    position: absolute;
    z-index: 4;
    cursor: pointer;
    bottom: 25px;
    right: 5px;
    width: 40px;
    height: auto;
    @media(min-width:768px){
      bottom: 30px;
      right: 60px;
      width: 60px;
    }
    &:hover{
      opacity: .9;
    }
  }
  &-frame{
    // overflow: hidden;
    mask: url('@/assets/img/barcelona/video-frame_ex.svg') no-repeat 0 0/100% 100%;
    width: 100%;
  }
}
@keyframes spinFront {
  50% {
    transform:rotate(360deg);
  }
}
</style>