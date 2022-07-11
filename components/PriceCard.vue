<template>
  <div class="fq-card">
    <h4>{{ title }}</h4>
    <p v-html="description"></p>
    <ul class="p-0 m-0">
      <li v-for="(item, index) in items" :key="`plan-item-${index}`" class="d-flex mb-3">
        <b-img src="check_icon.svg" class="mr-3" />
        <span>{{ item }}</span>
      </li>
    </ul>
    <div class="action">
      <a href="#contact">Iniciar teste agora!</a>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      required: true,
    },
    description: {
      type: String,
      required: true,
    },
    items: {
      type: Array,
      required: true,
    },
  }
}
</script>

<style lang="scss" scoped> 
.fq-card {
  display: flex;
  flex-direction: column;
  justify-content: center;
  
  align-items: center;
  padding: 25px;
  gap: 25px;

  width: 310px;
  height: 500px;

  background: #FFFFFF;
  box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.15);
  border-radius: 15px;

  transition: all 0.12s ease;

  &:hover {
    transform: scale(1.05);
  }

  h4 {
    font-weight: 800;
    font-size: 50px;
    line-height: 45px;

    letter-spacing: -0.01em;

    color: #12E066;
  }

  p {
    font-weight: 400;
    font-size: 14px;
    line-height: 17px;

    color: #282828;
  }

  ul {
    li {
      list-style: none;
      font-weight: 600;
      font-size: 14px;
      line-height: 17px;

      color: #000000;
    }
  }

  .action {
    a {
      padding: 13px 35px;
      font-weight: 700;
      font-size: 14px;
      line-height: 24px;

      text-transform: uppercase;

      color: #FFFFFF;

      background: #282828;
      border-radius: 60px;

      transition: all 0.15s ease;

      &:hover {
        text-decoration: none;
        color: #282828;
        background: #27FF7E;
      }
    }
  }
}
</style>