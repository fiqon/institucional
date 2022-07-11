<template>
  <b-container tag="section" id="header" class="pt-5">
    <b-row>
      <b-col cols="4">
        <p class="primary-phrase pt-4">Integração total para transformar o seu negócio.</p>
        <p class="secondary-phrase">Tenha acesso a uma forma inovadora de conexão entre serviços 100% personalizado para o seu negócio.</p>

        <a href="#contact" class="d-flex justify-content-between top-action w-100">
          <span>Começar</span>
          <b-img src="arrow_forward.svg" />  
        </a>
      </b-col>
      <b-col cols="8" class="text-right"><b-img class="w-100" src="header_image.svg" /></b-col>
    </b-row>
  </b-container>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
#header {
  max-height: 475px;
  @media screen and (min-width: 1200px) {
    max-height: 450px;
  }

  position: relative;
  z-index: 1;
}

.primary-phrase {
  font-weight: 700;
  font-size: 52.3167px;
  line-height: 59px;
  color: #fff;
}

.secondary-phrase {
  font-weight: 600;
  font-size: 20px;
  line-height: 26px;
  color: #000;
}

.top-action {
  background: #282828;
  border-radius: 60px;

  padding: 13px 22px;

  font-weight: 700;
  font-size: 20px;
  line-height: 24px;

  text-transform: uppercase;

  color: #12E066;
  
  transition: 0.12s ease;

  img {
    filter: invert(77%) sepia(57%) saturate(1874%) hue-rotate(84deg) brightness(92%) contrast(89%);
  }

  &:hover {
    text-decoration: none;
    color: #fff;

    img {
      filter: invert(100%);
    }
  }
}
</style>