<template>
  <section class="points">
    <div class="container">
      <div class="points-item">
        <h3>NOEGO</h3>
        <p>Beginners mind from start no finish? “you want to be rich? or do you want to be right?”</p>
      </div>
      <div class="points-item">
        <h3>LAPTOPLEARNING</h3>
        <p>Nothing is better than attendees and speakers have laptops out and are shoulder to shoulder showing and sharing</p>
      </div>
      <div class="points-item">
        <h3>NODOUCHEBAGS</h3>
        <p>NO Explanation needed</p>
      </div>
    </div>
  </section>
</template>
<script>
export default{

}
</script>
<style lang="scss" scoped>
.points{
  padding-top: 80px;
  @media(min-width:1200px){
    padding-top: 200px;
  }
  .container{
    display: flex;
    flex-wrap: wrap;
  }
  &-item{
    flex: 1 100%;
    &:not(:last-child){
      padding-bottom: 40px;
    }
    @media(min-width:768px){
      flex: 1 33.333%;
      &:not(:last-child){
        padding-bottom: 0;
      }
      padding-left: 32px;
      padding-right: 32px;
    }
  }
  h3{
    font-weight: 700;
    font-size: 25px;
    line-height: 28px;
    text-align: center;
    text-transform: uppercase;
    color: #FF3D00;
    margin-bottom: 15px;
    @media(min-width:768px){
      font-size: 30px;
      line-height: 34px;
    }
  }
  p{
    font-weight: 500;
    font-size: 18px;
    line-height: 21px;
    text-align: center;
    color: #FFFFFF;
    padding: 0 30px;
    @media(min-width:768px){
      padding: 0;
    }
  }
}
</style>