<template>
  <b-container tag="section" class="char">
    <b-row>
      <b-col cols="6" class="d-flex flex-column justify-content-between">
        <div>
          <div v-for="(item, index) in leftItems" :key="`char-left-item-${index}`" class="fq-card mb-5">
            <div class="title mb-3">{{ item.title }}</div>
            <div class="description" v-html="item.description"></div>
          </div>
        </div>
        <div>
          <b-img class="bottom-image" src="list_img.svg" />
          <b-img class="bottom-line" src="char_line.svg" />
        </div>
      </b-col>
      <b-col cols="6">
        <div v-for="(item, index) in rightItems" :key="`char-right-item-${index}`" class="fq-card mb-5">
          <div class="title mb-3">{{ item.title }}</div>
          <div class="description" v-html="item.description"></div>
        </div>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
export default {
  data() {
    return {
      leftItems: [
        {
          title: 'FLEXIBILIDADE',
          description: 'Com a possibilidade de flexibilizar o modo como as informações são transferidas e recebidas, seu time de desenvolvimento terá acesso a uma <strong>solução que se adapta a inúmeros cenários problemáticos.</strong>'
        },
        {
          title: 'CONTROLE',
          description: '<strong>Tenha acesso a todos os processos da sua integração.</strong> Saiba o que está funcionando ou não, quando ocorreu o erro, o que o originou, e os logs com os detalhes de cada evento realizado.'
        }
      ],
      rightItems: [
        {
          title: 'SEGURANÇA',
          description: '<strong>Estamos 100% dentro das atualizações da LGPD</strong>, garantindo não apenas rapidez na transferência de informações importantes, como também a segurança e privacidade de cada usuário presente na base de dados.'
        },
        {
          title: 'SEGURANÇA',
          description: '<strong>Estamos 100% dentro das atualizações da LGPD</strong>, garantindo não apenas rapidez na transferência de informações importantes, como também a segurança e privacidade de cada usuário presente na base de dados.'
        },
        {
          title: 'AGILIDADE',
          description: 'Dispensamos replicações ou redundâncias. Nosso sistema favorece a <strong>criação de um fluxo simples e ágil</strong>, com reaproveitamento de componentes (não precisa recriar o que foi criado).'
        },
        {
          title: 'MODULAR',
          description: '<strong>Nossa integração é 100% modular e customizável.</strong> Isso garante a aplicabilidade em diversos sistemas e possibilita que ela seja inserida em qualquer etapa do processo.'
        },
        {
          title: 'ACIONAMENTOS',
          description: '<strong>Na FiqOn você pode acionar o seu fluxo por meio de agendamentos, webhooks, chamada direta ou dísparo de eventos assíncronos.</strong><br /><br />E para todo fluxo você pode aplicar uma política de retry em caso de falha.'
        },
      ],
    }
  }
}
</script>

<style lang="scss" scoped>
.fq-card {
  .title {
    font-weight: 600;
    font-size: 18px;
    line-height: 24px;

    color: #12E066 !important;
  }

  .description {
    font-weight: 400;
    font-size: 15px;
    line-height: 23px;

    letter-spacing: 0.02em;

    color: #FFFFFF !important;
  }
}

.bottom-line {
  width: 950px;
  position: absolute;
  top: 520px;
  left: 200px;

  @media screen and (max-width: 1200px) {
    width: 700px;
    position: absolute;
    top: 662px;
    left: 260px;
  }
}

.bottom-image {
  position: relative;
  top: 60px;
  z-index: 2;
}
</style>