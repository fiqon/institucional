<template>
  <a :class="theme"><slot /></a>
</template>

<script>
export default {
  props: {
    theme: {
      type: String,
      default: 'dark',
    }
  }
}
</script>

<style lang="scss" scoped>
a {
  display: flex;
  flex-direction: row;
  align-items: center;

  border-radius: 60px;

  padding: 13px 22px;

  font-weight: 700;
  font-size: 20px;
  line-height: 24px;
  /* identical to box height, or 120% */

  text-transform: uppercase;

  &.dark {
    color: #12E066 !important;
    background-color: #282828;
  }

  &.light {
    color: #282828 !important;
    background-color: #12E066;
  }
}
</style>