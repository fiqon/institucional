<template>
  <b-container tag="nav" class="pt-4 fq-navbar d-flex">
    <div class="fq-brand"><b-img src="logo.svg" /></div>
    <ul class="fq-navbar-nav ml-auto d-none d-lg-block">
      <li v-for="(item, index) in navbarItems" :key="`navbar-item-${index}`" class="fq-navbar-item"><a :href="item.href">{{ item.title }}</a></li>
    </ul>
    <div class="d-lg-none ml-auto">
      <b-img src="menu.svg" @click="mobile_menu_shown = true" />
    </div>
    <div ref="mobile-menu" class="d-lg-none menu-overlay animate__animated animate__fadeInRight animate__faster" v-if="mobile_menu_shown">
      <div class="px-5">
        <div class="menu-header d-flex justify-content-between">
          <b-img src="logo_light.svg" />
          <b-img src="close_menu.svg" @click="disableMenu"/>
        </div>
        <div class="menu-content pt-5">
          <ul class="fq-navbar-nav-mobile pl-0 mt-5">
            <li v-for="(item, index) in navbarItems" :key="`navbar-item-${index}`" class="fq-navbar-item mb-4 ml-0 pl-0" @click="disableMenu"><a :href="item.href">{{ item.title }}</a></li>
          </ul>
        </div>
      </div>
    </div>
  </b-container>
</template>

<script>
import 'animate.css';

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
          'title': 'FAQ',
          'href': '#faq',
        },
        {
          'title': 'Contato',
          'href': '#contact',
        },
      ],
      mobile_menu_shown: false,
    }
  },
  methods: {
    disableMenu() {
      console.log(this.$refs['mobile-menu']);

      this.$refs['mobile-menu'].classList.add('animate__fadeOutRight')
      setTimeout(() => { this.mobile_menu_shown = false }, 500 )
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

        &:hover {
          text-decoration: none;
          color: rgba(0, 0, 0, 0.397);
          font-weight: 500;
        }
      }
    }
  }

  .fq-navbar-nav-mobile {
    li {
      list-style: none;

      a {
        font-weight: 500;
        font-size: 24px;
        line-height: 29px;
        text-transform: uppercase;

        color: #FFFFFF;

        &:hover {
          text-decoration: none;
          color: #e0e0e0;
        }
      }
    }
  }

  .menu-overlay {
    background-color: #5C5C5C;
    position: fixed;
    width: 100vw;
    height: 100vh;
    left: 0;
    top: 0;
    z-index: 3;

    padding-top: 95px !important;
  }
}
</style>
