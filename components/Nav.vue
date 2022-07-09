<template>
  <b-container tag="nav" class="pt-4 fq-navbar d-flex">
    <div class="fq-brand"><b-img src="logo.svg" /></div>
    <ul class="fq-navbar-nav ml-auto">
      <li v-for="(item, index) in navbarItems" :key="`navbar-item-${index}`" class="fq-navbar-item"><a :href="item.href">{{ item.title }}</a></li>
    </ul>
  </b-container>
</template>

<script>
export default {
  data() {
    return {
      navbarItems: [
        {
          'title': 'Início',
          'href': '#header',
        },
        {
          'title': 'Sobre',
          'href': '#about',
        },
        {
          'title': 'Planos',
          'href': '#plans',
        },
        {
          'title': 'Equipe',
          'href': '#team',
        },
        {
          'title': 'FAQ',
          'href': '#faq',
        },
        {
          'title': 'Contato',
          'href': '#contact',
        },
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
.fq-navbar {
  .fq-brand {
    display: inline-block;
  }

  .fq-navbar-nav {
    display: inline-block;

    .fq-navbar-item {
      display: inline-block;
      list-style: none;
      padding-left: 1.5rem;
      padding-right: 1.5rem;

      a {
        font-weight: 500;
        font-size: 14px;
        line-height: 17px;
        text-transform: uppercase;

        color: #000;
      }
    }
  }
}
</style>