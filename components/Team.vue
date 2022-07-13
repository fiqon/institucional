<template>
  <b-container tag="section">
    <b-row>
      <b-col lg="4" cols="12" class="mb-5">
        <h2>Conheça<br />nossa<br /> <strong>equipe</strong></h2>
      </b-col>
      <b-col lg="8" cols="12">
        <div class="image-container">
          <div v-for="(member, index) in members" :key="`team-member-${index}`" class="image d-lg-inline-block" :class="member.smol ? 'd-inline-block' : 'd-none'">
            <b-img :src="require(`~/static/${member.img}`)" />
            <div v-if="member.name" class="d-flex justify-content-end flex-column member-detail visible-mobile">
              <div>
                <p class="name">{{ member.name }}</p>
                <p class="position">{{ member.title }}</p>
              </div>
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
      members: [
        {
          img: 'team_asteristic.svg',
          smol: false,
        },
        {
          name: 'Andrey Postal',
          title: 'CO-FOUNDER & CTO',
          img: 'andrey.png',
          smol: true,
        },
        {
          name: 'Emerson Takakusa',
          title: 'CO-FOUNDER & CSO',
          img: 'taka.png',
          smol: true,
        },
        {
          name: 'Sérgio Moreira',
          title: 'CO-FOUNDER & COO',
          img: 'cerjo.png',
          smol: true,
        },
        {
          name: 'Wagner Wolff',
          title: 'BOARD MEMBER & CMO',
          img: 'wagner.png',
          smol: true,
        },
        {
          name: 'Ney Pereira',
          title: 'BOARD MEMBER',
          img: 'ney.png',
          smol: true,
        },
        {
          name: 'Gustavo Dropa',
          title: 'Tech lead Frontend',
          img: 'gustavo.png',
          smol: true,
        },
        {
          name: 'Matheus Oliveira',
          title: 'Head Backend',
          img: 'matheus.png',
          smol: true,
        },
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
h2 {
  font-weight: 400;
  font-size: 48px;
  line-height: 109%;

  letter-spacing: -0.02em;

  color: #282828;
}

.image-container {
  display: grid;

  grid-template-columns: repeat(2, 1fr);
  grid-template-rows: repeat(4, 1fr);

  @media screen and (min-width: 1200px) {
    grid-template-columns: repeat(4, 1fr);
    grid-template-rows: repeat(2, 1fr);
  }

  .image {
    position: relative;
    padding-bottom: 100%;

    &:first-of-type {
      img {
        width: auto;
        margin-left: 0px;
        margin-top: 30px;
      }
    }

    img {
      height: 100%;
      width: 100%;
      object-fit: cover;
      left: 0;
      position: absolute;
      top: 0;
    }

    &:hover {
      .member-detail {
        opacity: 1;
      }
    }

    .member-detail {
      transition: 0.12s ease;

      opacity: 0;

      background: #0000009c;
      background-blend-mode: multiply;

      &.visible-mobile {
        @media screen and (max-width: 992px) {
          opacity: 1;
          background: #00000056;
        }
      }

      position: absolute;
      height: 100%;
      width: 100%;
      object-fit: cover;

      .name {
        font-weight: 500;
        font-size: 20px;
        line-height: 23px;
        text-align: center;
        margin-bottom: 0.3rem;
        
        letter-spacing: -0.02em;

        color: #FFFFFF;
      }

      .position {
        font-weight: 300;
        font-size: 12px;
        line-height: 15px;
        margin-top: 0.3rem;

        letter-spacing: -0.02em;
        text-transform: uppercase;
        text-align: center;

        color: #FFFFFF;
      }
    }
  }
}
</style>