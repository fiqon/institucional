<template>
  <div>
    <Home />
    <div class="display-none">
      iwhf8r6c47ic5pk0gut6g8yhlj705t
    </div>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  mounted() {
    const script = document.createElement("noscript");
    const iframe = document.createElement("iframe");
    iframe.src = `https://www.googletagmanager.com/ns.html?id=${process.env.GTM}`;
    iframe.height = 0;
    iframe.width = 0;
    iframe.style = "display:none;visibility:hidden";
    script.appendChild(iframe);

    document.body.prepend(script);
  }
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');

* {
  font-family: 'Montserrat', sans-serif;

  scroll-behavior: smooth;
}

.large-rounded {
  border-radius: 14px;
}

.cursor-pointer {
  cursor: pointer !important;
}
</style>
