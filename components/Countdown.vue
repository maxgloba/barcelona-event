<template>
  <div class="countdown">
    <div class="countdown-time">{{ currentDate.days < 10 ? '0' + currentDate.days : currentDate.days }}<span>d</span></div>
    <div class="countdown-time">{{ currentDate.hours < 10 ? '0' + currentDate.hours : currentDate.hours }}<span>h</span></div>
    <div class="countdown-time">{{ currentDate.minutes < 10 ? '0' + currentDate.minutes : currentDate.minutes }}<span>m</span></div>
    <div class="countdown-time">{{ currentDate.seconds < 10 ? '0' + currentDate.seconds : currentDate.seconds }}<span>s</span></div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      currentDate: {},
      priceRanges: {
        2900: {
          start: '00:00:00, 13.05.2022',
          end: '23:59:59, 19.05.2022'
        },
        3000: {
          start: '00:00:00, 20.05.2022',
          end: '23:59:59, 26.05.2022'
        },
        3100: {
          start: '00:00:00, 27.05.2022',
          end: '23:59:59, 02.06.2022'
        },
        3200: {
          start: '00:00:00, 03.06.2022',
          end: '23:59:59, 09.06.2022'
        },
        3300: {
          start: '00:00:00, 10.06.2022',
          end: '23:59:59, 16.06.2022'
        },
        3400: {
          start: '00:00:00, 17.06.2022',
          end: '23:59:59, 23.06.2022'
        },
        3500: {
          start: '00:00:00, 24.06.2022',
          end: '23:59:59, 04.07.2022'
        }
      }
    }
  },
  mounted() {
    const keys = Object.keys(this.priceRanges)
    keys.forEach((key) => {
      const startDate = this.$moment(
        this.priceRanges[key].start,
        'HH:mm:ss, DD.MM.YYYY'
      )
      const endDate = this.$moment(
        this.priceRanges[key].end,
        'HH:mm:ss, DD.MM.YYYY'
      )
      const currentDate = this.$moment()
      if (
        (this.$moment(currentDate).isSame(startDate) ||
          this.$moment(currentDate).isAfter(startDate)) &&
        (this.$moment(currentDate).isBefore(endDate) ||
          this.$moment(currentDate).isSame(endDate))
      ) {
        localStorage.ticketPrice = key
        this.timer(startDate, endDate)
      }
    })
  },
  methods: {
    timer(start, end) {
      const x = setInterval(() => {
        const currentDate = this.$moment()
        const distanceMoment = end.diff(currentDate)
        if (distanceMoment > 0) {
          this.currentDate = {
            days: Math.floor(distanceMoment / (1000 * 60 * 60 * 24)),
            hours: Math.floor(
              (distanceMoment % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60)
            ),
            minutes: Math.floor(
              (distanceMoment % (1000 * 60 * 60)) / (1000 * 60)
            ),
            seconds: Math.floor((distanceMoment % (1000 * 60)) / 1000),
          }
        } else {
          clearInterval(x)
        }
      }, 1000)
    },
  },
}
</script>

<style scoped lang="scss">
.countdown {
  display: flex;
  color: #fff;
  &-time {
    margin: 0;
    font-weight: 400;
    font-size: 30px;
    line-height: 1;
    letter-spacing: 0.095em;
    min-width: 60px;
    &:not(:first-child){
      margin-left: 5px;
    }
    @media (min-width: 768px) {
      font-size: 30px;
      line-height: 35px;
    }
    span {
      font-size: 18px;
      font-weight: 300;
      color: #FF3D00;
      @media(min-width:768px){
        font-size: 23px;
      }
    }
  }
}
</style>
