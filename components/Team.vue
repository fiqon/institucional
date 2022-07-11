<template>
  <b-container tag="section">
    <b-row>
      <b-col cols="4">
        <h2>Conheça<br />nossa<br /> <strong>equipe</strong></h2>
      </b-col>
      <b-col cols="8">
        <div class="image-container">
          <div v-for="(member, index) in members" :key="`team-member-${index}`" class="image">
            <b-img :src="require(`~/static/${member.img}`)" />
            <div v-if="member.name" class="d-flex justify-content-end flex-column member-detail">
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
        },
        {
          name: 'Andrey Postal',
          title: 'CO-FOUNDER & CTO',
          img: 'andrey.png',
        },
        {
          name: 'Emerson Takakusa',
          title: 'CO-FOUNDER & CSO',
          img: 'taka.png',
        },
        {
          name: 'Sérgio Moreira',
          title: 'CO-FOUNDER & COO',
          img: 'cerjo.png',
        },
        {
          name: 'Wagner Wolff',
          title: 'BOARD MEMBER & CMO',
          img: 'wagner.png',
        },
        {
          name: 'Ney Pereira',
          title: 'BOARD MEMBER',
          img: 'ney.png',
        },
        {
          name: 'Gustavo Dropa',
          title: 'Tech lead Frontend',
          img: 'gustavo.png',
        },
        {
          name: 'Matheus Oliveira',
          title: 'Head Backend',
          img: 'matheus.png',
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
  grid-template-columns: repeat(4, 1fr);
  grid-template-rows: repeat(2, 1fr);

  .image {
    position: relative;
    padding-bottom: 100%;
    height: 226px;

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

      position: relative;
      height: 226px;

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