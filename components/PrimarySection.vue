<template>
  <b-container tag="section" id="header" class="pt-5">
    <b-row>
      <b-col cols="12" lg="4">
        <p class="primary-phrase pt-4">Integração total que traz agilidade, organização e resultados.</p>
        <p class="secondary-phrase">Tenha acesso a uma forma inovadora de conexão entre serviços 100% personalizado para o seu negócio.</p>

        <a href="#contact" class="d-none d-lg-flex justify-content-between top-action w-100">
          <span>Começar</span>
          <b-img src="arrow_forward.svg" />  
        </a>
      </b-col>
      <b-col cols="12" lg="8" class="text-center">
        <b-img class="w-100 d-none d-lg-block" src="header_image.svg" />
        <b-img class="h-100 mobile-max-w d-inline-block d-lg-none pb-4" src="header_image_mobile.svg" />
      </b-col>
      <b-col cols="12" class="d-block d-lg-none">
        <a href="#contact" class="d-flex justify-content-between top-action w-100">
          <span>Começar</span>
          <b-img src="arrow_forward.svg" />  
        </a>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
.mobile-max-w {
  max-width: 100%;
}

#header {
  max-height: 850px;

  @media screen and (min-width: 480px) {
    max-height: 710px;
  }

  @media screen and (min-width: 992px) {
    max-height: 475px;
  }

  @media screen and (min-width: 1200px) {
    max-height: 450px;
  }

  position: relative;
  z-index: 1;
}

.primary-phrase {
  font-weight: 700;
  font-size: 45.3167px;
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
