<template>
  <div>
    <b-container fluid tag="section">
      <h3>Conheça nossos <strong>planos</strong>:</h3>
      <div class="prices-container text-center mt-5 pb-5">
        <div class="overflow-prices d-inline-block">
          <div v-for="(plan, index) in plans" :key="`plan-${index}`" class="d-inline-block">
            <PriceCard
              class="mr-4"

              v-bind="plan"
            />
          </div>
        </div>
      </div>
    </b-container>
    <b-container tag="section">
      <div class="ideal-plan mt-5 d-none d-lg-block">
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

      <div class="ideal-plan-mobile mt-5 d-lg-none">
        <b-img src="fat_asteristic.svg" class="thicc-asteristic mt-4" />
        <div class="ideal-plan-card p-3">
          <div>
            <h3>Não encontrou o plano ideal?</h3>
            <p class="my-3">Se nenhuma das opções se encaixa com a sua necessidade, fale com o nosso consultor e saiba como podemos te ajudar.</p>
            <div class="text-center btn-action button-spacing">
              <a href="#contact">Personalize a sua integração agora mesmo!</a>
            </div>
          </div>
        </div>
      </div>
    </b-container>
  </div>
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
          description: 'Feito para quem precisa de mais opções de eventos e requisições, buscando o equilíbrio.',
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

.prices-container {
  overflow: auto;

  &::-webkit-scrollbar {
    display: none;
  }
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

.ideal-plan-mobile {
  text-align: center;

  .thicc-asteristic {
    width: 338px;
  }

  .ideal-plan-card {
    background: #282828;
    border-radius: 15px;

    width: calc(100% );
    padding-top: 110px !important;
    margin-top: -150px;

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

    .btn-action {
      padding: 13px 55px;
      cursor: pointer;

      border: 1px solid #FFFFFF;
      border-radius: 60px;

      &:hover {
        background: #27FF7E;
        border-color: #27FF7E;

        a {
          text-decoration: none;
          color: #282828;
        }
      }

      a {
        font-weight: 700;
        font-size: 16px;
        line-height: 24px;

        text-transform: uppercase;

        color: #FFFFFF;

        transition: all 0.15s ease;
      }
    }

    .button-spacing {
      margin-top: 2.5rem;
      margin-bottom: 1.5rem;
    }
  }
}

.overflow-prices {
  width: max-content;
  padding-left: 50px;
  padding-right: 30px;
  padding-top: 50px;
}
</style>