<template>
  <li class="all-quotes__element">{{ quoteText.text }}</li>
</template>

<script>
  export default {
    props: {
      quoteText: {
        type: Object,
        required: true
      }
    }
  }
</script>

<style lang="scss">
  .all-quotes {

    &__element {
      display: inline-block;
      border: 1px solid #aaa;
      padding: 15px;
      border-radius: 6px;
      font-size: 25px;
      font-family: 'VT323', sans-serif;
      width: 225px;
      text-align: center;
      margin-left: 10px;
      margin-bottom: 10px;
      cursor: pointer;
      word-wrap: break-word;

      &:hover {
        background-color: lightcyan;
      }
    }
  }
</style>