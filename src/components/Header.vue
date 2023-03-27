<template>
  <header>
    <img src="@/assets/_images/header/godfather_header.jpg" alt="header" />
  </header>
</template>

<style lang="scss">
  header {
    height: 30vh;
    overflow: hidden;
    position: relative;
    z-index: 2;
    &:after {
      position: absolute;
      left: 0;
      bottom: 0;
      height: 50px;
      width: 100%;
      box-shadow: inset 0px -41px 11px -1px rgba(0, 0, 0, 0.5);
      z-index: 2;
      content: "";
    }
    img {
      margin-top: -30vh;
    }
  }
</style>