<template>
  <section class="schedule">
    <div class="container">
      <div class="sqrs">
        <span class="sqrs-left"></span>
        <span class="sqrs-right"></span>
        <span class="sqrs-left"></span>
      </div>
      <h2>What’s THE SCHEDULE?</h2>
      <h4>Fabrica Moritz - Ronda Sant Antoni, 41, 08011 Barcelona</h4>
      <div class="schedule-item">
        <div class="left">
          <svg width="585" height="221" viewBox="0 0 585 221" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M15 0.121583L15 15.1216L-1.31134e-06 15.1216L0 30.1216L15 30.1216L15 63.1216L3.05981e-06 63.1216L3.04917e-06 205.122L15 205.122L15 220.122L84 220.122L84 205.122L410 205.122L410 220.122L585 220.122L585 15.1216L570 15.1216L570 0.121632L516 0.121632L516 15.1216L501 15.1216L501 0.121632L15 0.121583Z" fill="#FF3D00"/>
          </svg>
          <h3 class="title">july 2</h3>
        </div>
        <div class="right">
          <ul>
             <li><b>18:30-20:30</b> - Welcome Party</li>
          </ul>
        </div>
      </div>
      <div class="schedule-item">
        <div class="left">
          <svg width="585" height="221" viewBox="0 0 585 221" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M15 16.1216L16 16.1216L16 15.1216L16 1.12158L500 1.12163L500 15.1216L500 16.1216L501 16.1216L516 16.1216L517 16.1216L517 15.1216L517 1.12163L569 1.12163L569 15.1216L569 16.1216L570 16.1216L584 16.1216L584 219.122L411 219.122L411 205.122L411 204.122L410 204.122L84 204.122L83 204.122L83 205.122L83 219.122L16 219.122L16 205.122L16 204.122L15 204.122L1 204.122L1 64.1216L15 64.1216L16 64.1216L16 63.1216L16 30.1216L16 29.1216L15 29.1216L1 29.1216L0.999999 16.1216L15 16.1216Z" stroke="#FF3D00" stroke-width="2"/>
          </svg>
          <h3 class="title">july 3</h3>
        </div>
        <div class="right">
          <ul>
            <li><b>07:30-08:15</b> - Breakfast</li>
            <li><b>08:20-11:35</b> - Education</li>
            <li><b>11:40-13:00</b> - Lunch</li>
            <li><b>13:05-16:00</b> - Education</li>
            <li><b>16:00-18:00</b> - Small Group Tapas Tour</li>
            <li><b>18:00-20:00</b> - Networking and Drinks</li>
          </ul>
        </div>
      </div>
      <div class="schedule-item">
        <div class="left">
          <svg width="585" height="221" viewBox="0 0 585 221" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M15 0.121583L15 15.1216L-1.31134e-06 15.1216L0 30.1216L15 30.1216L15 63.1216L3.05981e-06 63.1216L3.04917e-06 205.122L15 205.122L15 220.122L84 220.122L84 205.122L410 205.122L410 220.122L585 220.122L585 15.1216L570 15.1216L570 0.121632L516 0.121632L516 15.1216L501 15.1216L501 0.121632L15 0.121583Z" fill="#FF3D00"/>
          </svg>
          <h3 class="title">july 4</h3>
        </div>
        <div class="right">
          <ul>
            <li><b>09:00-10:00</b> - Breakfast</li>
            <li><b>10:05-12:25</b> - Education</li>
            <li><b>12:30-13:40</b> - Lunch</li>
            <li><b>13:45-16:15</b> - Education</li>
            <li><b>18:00-20:00</b> - Networking and Drinks</li>
          </ul>
        </div>
      </div>
    </div>
  </section>
</template>
<script>
export default{

}
</script>
<style lang="scss" scoped>
.schedule{
  padding: 80px 0 0;
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
    margin-bottom: 10px;
    padding-left: 30px;
    @media(min-width:992px){
      padding-left: 60px;
      font-size: 70px;
      line-height: 66px;
      margin-bottom: 20px;
      margin-left: 50%;
    }
  }
  h4{
    font-weight: 500;
    font-size: 16px;
    line-height: 1;
    color: #FFFFFF;
    margin-bottom: 40px;
    padding-left: 30px;
    @media(min-width:992px){
      padding-left: 60px;
      font-size: 20px;
      margin-bottom: 60px;
      margin-left: 50%;
    }
  }
  &-item{
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
    &:not(:last-child){
      padding-bottom: 30px;
    }
    @media(min-width:768px){
      padding: 0;
      &:not(:last-child){
        padding-bottom: 60px;
      }
    }
    svg{
      max-width: 100%;
      height: auto;
    }
    h3{
      font-size: 25px;
      font-weight: 700;
      line-height: 66px;
      text-align: center;
      text-transform: uppercase;
      position: absolute;
      left: 50%; top: 50%;
      transform: translate(-50%, -50%);
      @media(min-width:768px){
        font-size: 50px;
      }
      @media(min-width:992px){
        font-size: 70px;
      }
    }
    .left, .right{
      position: relative;
      flex: 1 100%;
      width: 100%;
      @media(min-width:768px){
        flex: 1 50%;
        width: 50%;
      }
    }
    ul{
      list-style: none;
      padding-left: 30px;
      padding-top: 25px;
      @media(min-width:768px){
        padding-left: 45px;
        padding-top: 0;
      }
      li{
        font-weight: 400;
        font-size: 18px;
        line-height: 1.2;
        color: #FFFFFF;
      }
    }
  }
}
</style>