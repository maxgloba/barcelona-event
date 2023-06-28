<template>
  <header class="header">
    <div class="container">
      <svg class="header-logo" width="146" height="79" viewBox="0 0 146 79" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M71.0635 32.1441H40.978V28.9286H37.6328V3.21693H40.978V0H71.0743V6.42347H51.0075V12.8558H61.0355V19.2882H51.0075V25.7117H71.0635V32.1441Z" fill="white"/>
        <path d="M108.275 32.1441H78.1791V28.9286H74.8323V3.21693H78.1791V0H108.275V6.42347H88.2179V12.8558H98.2458V19.2882H88.2179V25.7117H108.275V32.1441Z" fill="white"/>
        <path d="M146 32.0761H132.555V19.2439H125.838V32.0761H112.393V0H125.838V12.8322H132.555V0H146V12.8322H142.636V19.2439H146V32.0761Z" fill="white"/>
        <path d="M33.4323 32.125H3.33597V28.9091H0V3.21592H3.34678V0H33.4415V6.42144H13.3748V25.6947H20.0575V19.2732H16.7107V12.8518H33.4323V32.125Z" fill="white"/>
        <path d="M45.9514 74.6046H41.3598V78.9897H4.59159V74.6046H0V39.4898H4.59159V35.1047H41.3598V39.4898H45.9514V74.6046ZM27.5727 70.2195V43.8852H18.3787V70.2195H27.5727Z" fill="white"/>
        <path d="M96.249 74.6046H91.6574V78.9897H54.8784V74.6046H50.2868V35.1047H68.6655V70.2195H77.8595V35.1047H96.2382L96.249 74.6046Z" fill="white"/>
        <path d="M145.999 43.8852H132.213V79H113.835V43.8852H100.048V35.1047H145.999V43.8852Z" fill="white"/>
      </svg>
    </div>
  </header>
</template>
<script>
export default{

}
</script>
<style lang="scss" scoped>
.header{
  padding-top: 10px;
  position: absolute;
  left: 0;
  top: 0;
  width: 100%;
  z-index: 10;
  @media(min-width:768px){
    padding-top: 60px;
  }
  svg{
    height: 57px;
    width: auto;
    @media(min-width:768px){
      height: 79px;
    }
  }
  .container{
    display: flex;
    justify-content: space-between;
  }
}
</style>