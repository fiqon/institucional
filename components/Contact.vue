<template>
  <b-container>
    <b-row>
      <b-col cols="12" lg="6">
        <h2 class="title mb-5">Vamos integrar as suas ferramentas e começar a automatizar os seus processos?</h2>
        <p class="description"><strong>Preencha o formulário para conversar com um dos nossos consultores.</strong> Eles vão analisar e te auxiliar a encontrar a solução ideal para ter um fluxo de trabalho mais produtivo.</p>
      </b-col>
      <b-col cols="12" lg="6">
        <b-form @submit.prevent="submitForm">
          <b-form-group>
            <b-input placeholder="Meu nome" @focusout="showErrors.nome = webhookInfo.nome.length <= 0;" v-model="webhookInfo.nome" />
            <div class="text-right text-danger" v-if="showErrors.nome"><small>Por favor, informe o seu nome.</small></div>
          </b-form-group>
          <b-form-group>
            <b-input placeholder="Nome da minha empresa" @focusout="showErrors.empresa = webhookInfo.empresa.length <= 0;" v-model="webhookInfo.empresa" />
            <div class="text-right text-danger" v-if="showErrors.empresa"><small>Por favor, informe o nome da sua empresa.</small></div>
          </b-form-group>
          <b-form-group>
            <b-input type="email" placeholder="Meu email para contato" @focusout="showErrors.email = webhookInfo.email.length <= 0;" v-model="webhookInfo.email" />
            <div class="text-right text-danger" v-if="showErrors.email"><small>Por favor, informe o seu email.</small></div>
          </b-form-group>
          <b-form-group>
            <b-textarea placeholder="Mensagem" rows="7" @focusout="showErrors.mensagem = webhookInfo.mensagem.length <= 0;" v-model="webhookInfo.mensagem" />
            <div class="text-right text-danger" v-if="showErrors.mensagem"><small>Por favor, informe a sua mensagem.</small></div>
          </b-form-group>
          <div class="d-flex justify-content-end">
            <recaptcha />
          </div>
          <div class="text-right text-danger" v-if="showErrors.token"><small>Por favor, resolva o captcha.</small></div>

          <button class="w-100 d-flex justify-content-between mt-3 action-button" type="submit">Entrar em contato <b-img class="mt-1" src="arrow_forward.svg" /></button>
        </b-form>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
export default {
  data() {
    return {
      webhookInfo: {
        token: "",
        nome: "",
        empresa: "",
        email: "",
        mensagem: "",
      },
      showErrors: {
        token: false,
        nome: false,
        empresa: false,
        email: false,
        mensagem: false,
      }
    };
  },
  methods: {
    async submitForm() {
      try {
        const token = await this.$recaptcha.getResponse()
        this.showErrors.token = false;

        this.webhookInfo.token = token;

        let proceed = true;
        Object.keys(this.webhookInfo).forEach((el) => {
          if(this.webhookInfo[el].length <= 0) {
            this.showErrors[el] = true;
            proceed = false;
          } else {
            this.showErrors[el] = false;
          }
        });

        if(!proceed) {
          return;
        }

        let { email, nome, empresa, mensagem } = this.webhookInfo

        this.$axios(
          {
            method: 'post',
            // url: process.env.WEBHOOK_FIQON,
            url: "https://instance.v2.fique.online/webhook/4f21010e-f698-4aab-a5c2-b5757b2575e2/form_submit?token=fe507a43a1da2f741d91d2e47e24da37e0cd8fa6d9360b7dae404e",
            data: {
              "contact": {
                  "email": email,
                  "firstName": nome.split('')[0],
                  "lastName": nome.split('').at(-1) || null,
                  "phone": null,
                  "fieldValues": [
                      {
                          "title": "Nome Empresa",
                          "field": "1",
                          "value": empresa
                      },
                      {
                          "title": "Mensagem",
                          "field": "2",
                          "value": mensagem
                      }
                  ]
              }
            },
            withCredentials: false,
          }
        ).then(() => {
          this.$swal('Mensagem enviada!', 'Em breve um de nossos consultores entrará em contato.', 'success');

          this.webhookInfo = {
            token: "",
            nome: "",
            empresa: "",
            email: "",
            mensagem: "",
          };
        })
        .catch(() => {
          this.$swal('Ocorreu um problema!', 'Algo deu errado enquanto tentávamos enviar a mensagem :(', 'error');
        });
        
        await this.$recaptcha.reset()
      } catch(error) {
        console.error(error);
        this.showErrors.token = true;
      }
    }
  }
};
</script>

<style lang="scss" scoped>
h2 {
  &.title {
    font-weight: 700;
    font-size: 40px;
    line-height: 48px;

    color: #12E066;
  }
}

p {
  &.description {
    font-weight: 400;
    font-size: 16px;
    line-height: 28px;

    color: #282828;
  }
}

.action-button {
  border: none;
  background: #12E066;
  border-radius: 60px;  
  font-weight: 800;
  padding: 13px 22px;

  font-size: 20px;
  line-height: 24px;

  text-transform: uppercase;

  color: #282828;

  transition: all 0.15s ease;

  &:hover {
    background: #282828;
    color: #12E066;

    img {
      filter: invert(77%) sepia(57%) saturate(1874%) hue-rotate(84deg) brightness(92%) contrast(89%);
    }
  }
}
</style>