<template>
  <b-container tag="section" id="plans">
    <h3>Conheça nossos <strong>planos</strong>:</h3>
    <div class="d-flex justify-content-around mt-5">
      <PriceCard
        v-for="(plan, index) in plans" :key="`plan-${index}`"

        v-bind="plan"
      />
    </div>
    <div class="ideal-plan mt-5">
      <b-img src="fat_asteristic.svg" class="thicc-asteristic mt-4" />
      <div class="ideal-plan-card p-3">
        <div>
          <h3>Não encontrou o plano ideal?</h3>
          <p class="my-3">Se nenhuma das opções se encaixa com a sua necessidade, fale com o nosso consultor e saiba como podemos te ajudar.</p>
          <div class="text-center button-spacing">
            <a href="#contact">Personalize a sua integração agora mesmo!</a>
          </div>
        </div>
      </div>
    </div>
  </b-container>
</template>

<script>
export default {
  data() {
    return {
      plans: [
        {
          title: 'Basic Worker',
          description: 'Ideal para você que tem urgência <strong>e precisa integrar plataformas agora mesmo!</strong>',
          items: [
            'Acesso às funcionalidades e aos módulos pré-construídos',
            'Mínimo 14 dias de logs',
            'Limite de eventos começando em 10.000',
          ]
        },
        {
          title: 'Inter Company',
          description: 'Feito para quem precisa de mais opções de eventos e requisições.',
          items: [
            'Acesso às funcionalidades e aos módulos pré-construídos',
            'Mínimo 14 dias de logs',
            'Limite de eventos começando em 10.000',
          ]
        },
        {
          title: 'High Request',
          description: 'Pensado para a alta demanda de resposta e transferência de dados, com ainda mais eventos.',
          items: [
            'Acesso às funcionalidades e aos módulos pré-construídos',
            'Mínimo 14 dias de logs',
            'Limite de eventos começando em 50.000',
          ]
        },
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
h3 {
  font-weight: 400;
  font-size: 18px;
  line-height: 22px;

  text-align: center;

  color: #A0A0A0;
}

.ideal-plan {
  .thicc-asteristic {
    float: left;
    width: 338px;
  }

  .ideal-plan-card {
    background: #282828;
    border-radius: 15px;

    width: calc(100% - 210px);
    margin-left: 105px;

    h3 {
      font-weight: 800;
      font-size: 35px;
      line-height: 43px;

      text-align: center;

      color: #12E066;
    }

    p {
      font-weight: 400;
      font-size: 14px;
      line-height: 17px;

      text-align: center;

      color: #FFFFFF;
    }

    a {
      font-weight: 700;
      font-size: 16px;
      line-height: 24px;
      padding: 13px 55px;

      text-transform: uppercase;

      color: #FFFFFF;

      border: 1px solid #FFFFFF;
      border-radius: 60px;

      transition: all 0.15s ease;

      &:hover {
        text-decoration: none;
        color: #282828;
        background: #27FF7E;
        border-color: #27FF7E;
      }
    }

    .button-spacing {
      margin-top: 2.5rem;
      margin-bottom: 1.5rem;
    }
  }
}
</style>