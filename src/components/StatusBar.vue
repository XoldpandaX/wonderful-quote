<template>
  <div class="status">
    <h1 class="status__title">Quotes Added</h1>
    <div class="status-bar">
      <div class="status-bar__line"
           :style="{ width: statusLineWidth + '%', borderRadius: statusLineBorderRadius}">
        <div class="status-bar__text">{{ quotesStatus.addedQuotes }}/{{ quotesStatus.maxQuotes }}</div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    props: {
      quotesStatus: {
        type: Object,
        required:true
      }
    },
    computed: {
        statusLineWidth() {
            return this.quotesStatus.addedQuotes * 10;
        },
        statusLineBorderRadius() {
            return this.quotesStatus.addedQuotes === 10 ? '6px' : '5px 0 0 5px';
        }
    }
  }
</script>

<style lang="scss">
  h1 {
    text-align: left;
    margin-bottom: 10px;
    padding-left: 10px;
    color: #42b983;
  }

  .status-bar {
    position: relative;
    height: 22px;
    background-color: #E8E8E8;
    border-radius: 6px;
    box-shadow: inset 0 1px 3px;

    &__line {
      background-color: cornflowerblue;
      width: 10%;
      height: 22px;
      border-radius: 5px 0 0 5px;
      transition: width 300ms;
    }

    &__text {
      line-height: 22px;
      padding-left: 49%;
      font-weight: bold;
      color: white;
      font-size: 15px;
    }
  }
</style>