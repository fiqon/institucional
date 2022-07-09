<template>
  <b-container tag="section" class="pt-5 mt-5">
    <b-row>
      <b-col cols="5"><b-img class="large-rounded" fluid src="chain.gif" /></b-col>
      <b-col cols="7">
        <div class="mt-5">
          <div v-for="(item, index) in items" :key="`chain-gif-item-${index}`" class="fq-card p-4 mb-4">
            <div class="icon"><b-img :src="require(`~/static/${item.icon}`)" /></div>
            <div class="content">
              <div class="title mb-2">{{ item.title }}</div>
              <div class="description">{{ item.description }}</div>
            </div>
          </div>
        </div>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
export default {
  data() {
    return {
      items: [
        {
          icon: 'settings_icon.svg',
          title: 'Fluxo personalizado',
          description: 'Identificamos o problema e encontramos a melhor solução para o seu negócio. Nossa tecnologia é capaz de se adaptar a todas as necessidades de integração. Tudo isso em uma plataforma atualizada e dinâmica.'
        },
        {
          icon: 'scale_icon.svg',
          title: 'Escalável',
          description: 'Com a flexibilidade da nossa ferramenta, é possível incorporar facilmente novos requisitos de forma ágil e segura.'
        },
      ],
    }
  }
}
</script>

<style lang="scss" scoped>
.fq-card {
  background: #FFFFFF;
  box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.15), 0px 0px 30px rgba(0, 0, 0, 0.1);
  border-radius: 10px;
  display: flex;

  .icon {
    width: 150px;
  }

  .content {
    width: calc(100% - 160px);

    .title {
      font-weight: 600;
      font-size: 18px;
      line-height: 24px;
      color: #12E066;
    }

    .description {
      font-weight: 300;
      font-size: 15px;
      line-height: 20px;

      letter-spacing: 0.02em;
    }
  }
}
</style>