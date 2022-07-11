<template>
  <div>
    <header>
      <Nav />
      <PrimarySection />
    </header>
    <div class="header-divisor"></div>
    <div id="about" class="section-1 text-center mt-5 pt-5">
      <h2>Menos trabalho, mais resultados.</h2>
      <h3>Integre <strong>todas as suas ferramentas</strong> sem complicações.</h3>
    </div>
    <GIFSection />
    <div class="mt-5 char">
      <div class="char-divisor top"></div>
      <div class="bg-char">
        <Characteristics />
      </div>
      <div class="char-divisor bottom"></div>
    </div>
    <div class="section-2 text-center mt-5 pt-5">
      <h3>Chegou a hora de eliminar as tarefas chatas,</h3>
      <h2>nós vamos fazer isso por você!</h2>
    </div>
    <Prices class="pt-5"/>
    <div id="team" class="p-5 mt-5">
      <Team />
    </div>
    <div id="faq" class="p-5">
      <FAQ />
    </div>
    <div id="contact" class="pt-5 pb-0">
      <Contact />
      <Footer />
    </div>
  </div>
</template>

<script>
</script>

<style lang="scss">
header {
  background-color: #12E066;
}

.header-divisor {
  height: 100px;
  background-image: url("~/static/header_divisor.svg");
  background-size: cover;
  background-position: bottom;
  position: relative;
}

.char {
  .char-divisor {
    height: 100px;
    background-image: url("~/static/char_divisor.svg");
    background-size: cover;
    position: relative;

    &.top {
      background-position: top;
    }

    &.bottom {
      background-position: bottom;
    }
  }
  
  .bg-char {
    background-color: #282828;
  }
}

.section-1 {
  h2 {
    font-weight: 700;
    font-size: 36px;
    line-height: 44px;
    text-align: center;

    color: #12E066;
  }

  h3 {
    font-weight: 400;
    font-size: 22px;
    line-height: 27px;
    text-align: center;

    color: #282828;
  }
}

.section-2 {
  h3 {
    font-weight: 600;
    font-size: 26px;
    line-height: 32px;
    text-align: center;
    letter-spacing: -0.02em;

    color: #A0A0A0;
  }

  h2 {
    font-weight: 800;
    font-size: 46px;
    line-height: 56px;
    text-align: center;
    letter-spacing: -0.02em;

    color: #282828;
  }
}

#team {
  background: linear-gradient(89.49deg, #10DA68 67.36%, #27FF7E 98.55%);
}

#faq {
  background-color: #1A1F31;
  background-image: url("~/static/background_faq.svg");
  background-repeat: no-repeat;
  background-position: right;
}

#contact {
  background-image: url("~/static/background_contact.svg");
  background-repeat: no-repeat;
  background-position: bottom left;
}
</style>