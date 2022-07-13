<template>
  <b-container tag="footer" class="px-5 pt-5 mt-5">
    <b-row>
      <b-col cols="4">
        <address>
          <p class="mb-1">Rua Jacob Holzmann, 233</p>
          <p>Edif. Philadelphia • Ponta Grossa/PR</p>
        </address>
      </b-col>
      <b-col cols="4" class="text-center">
        <b-img src="logo_light.svg" />
      </b-col>
      <b-col cols="4" class="text-center">
        <a class="d-inline-block" href="mail:contato@fique.online"><strong>contato@</strong>fique.online</a>
      </b-col>
    </b-row>
    <b-row class="mt-5 py-3">
      <b-col>
        <p class="text-center footer-ending">FiqOn © Todos os Direitos Reservados 2022</p>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
footer {
  background: #282828;
  border-radius: 15px 15px 0px 0px;

  @media screen and (max-width: 1200px) {
    width: 100% !important;
    max-width: 100% !important;
    margin-left: 0 !important;
    margin-right: 0 !important;
  }
  
  p, a {
    font-weight: 400;
    font-size: 14px;
    line-height: 17px;

    color: #FFFFFF;

    &.footer-ending {
      font-weight: 300;
      font-size: 12px;
      line-height: 15px;

      text-align: center;

      color: #696969;
    }
  }
}
</style>