<template>
  <b-container tag="section" class="py-3">
    <b-row>
      <b-col cols="12">
        <h2 class="my-5"><span>FAQ</span> Perguntas Frequentes</h2>
      </b-col>
      <b-col lg="8" cols="12" class="mt-5">
        <div v-for="(q, index) in questions" :key="`question-faq-${index}`" class="fq-question-card mb-4">
          <h3 @click="q.open = !q.open" class="title d-flex justify-content-between cursor-pointer mb-0 p-3">{{ q.question }} <b-img :class="q.open ? 'invert-arrow' : ''" src="arrow_back_icon.svg" /></h3>
          <b-collapse :visible="q.open">
            <p class="description px-3" v-html="q.answer"></p>
          </b-collapse>
        </div>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
export default {
  data() {
    return {
      questions: [
        {
          question: "Posso cancelar o meu plano a qualquer momento?",
          answer: "<strong>Sim, não existe tempo mínimo de contrato ou fidelidade.</strong> Você pode cancelar quando quiser. Deixamos você livre para nos escolher sempre que precisar de nossa integração e consultas adicionais.",
          open: false,
        },
        {
          question: "Eu posso modificar o meu plano após a contratação?",
          answer: "<strong>Sim, você tem total liberdade para fazer upgrade ou downgrade em seu plano quando quiser.</strong> Mas, antes de formalizar uma decisão, recomendamos que converse com um dos nossos consultores para avaliar a real necessidade do seu negócio.",
          open: false,
        },
        {
          question: "Quantas ferramentas posso integrar com a FiqOn?",
          answer: "<strong>Não existe limites de sistemas integrados na FiqOn, você pode fazer a integração com quantos quiser!</strong> Existe apenas a limitação de requisição e de dados trafegados.",
          open: false,
        },
        {
          question: "O suporte demora para responder às minhas solicitações?",
          answer: "<strong>Não!</strong> Nós entendemos que o seu tempo é valioso, por isso priorizamos o atendimento para resolver qualquer problema que esteja aparecendo.",
          open: false,
        },
        {
          question: "Existe um manual ou treinamento para lidar com a integração?",
          answer: "<strong>Sim, após a contratação compartilhamos um tutorial com você, demonstrando como a integração funciona.</strong> Também enviamos um manual com as melhores práticas, para preservar o plano contratado.",
          open: false,
        },
        {
          question: "Como saber qual é o plano ideal para a minha necessidade?",
          answer: "<strong>Os nossos consultores estão preparados para te atender e te explicar quais as integrações que precisam ser feitas para otimizar os seus processos e como nós podemos te ajudar.</strong>",
          open: false,
        },
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
.fq-question-card {
  background-color: #1A1F31;
  border: 1px solid #FFFFFF;
  border-radius: 10px;

  .title {
    font-weight: 600;
    font-size: 18px;
    line-height: 24px;

    color: #12E066;

    img {
      transform: rotate(0);

      transition: all 0.2s;

      &.invert-arrow {
        transform: rotate(180deg);
      }
    }
  }

  .description {
    font-weight: 400;
    font-size: 15px;
    line-height: 23px;

    letter-spacing: 0.02em;

    color: #FFFFFF;
  }
}

h2 {
  font-weight: 300;
  font-size: 36px;
  line-height: 44px;

  color: #fff;
  
  span {
    font-weight: 900;
    font-size: 36px;
    line-height: 44px;

    color: #12E066;
  }
}
</style>