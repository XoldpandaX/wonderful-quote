<template>
  <div class="all-quotes">
    <ul>
      <quote v-for="(obj, index) in quotesText"
             :quoteText="obj" @click.native="deleteQuote(index)"></quote>
    </ul>
  </div>
</template>

<script>
  import Quote from './Quote.vue';

  export default {
    components: {
      Quote
    },
    props: {
      quotesText: {
        type: Array,
        required: true
      },
      quotesStatus: {
      	type: Object,
        required: true
      }
    },
    methods: {
    	deleteQuote(index) {
          this.quotesStatus.addedQuotes--;
          this.$emit('quoteTextForDelete', index);
    	}
    }
  }
</script>

<style lang="scss">
  .all-quotes {

    ul {
      margin: 0;
      padding: 0;
      display: flex;
      flex-wrap: wrap;
    }
  }
</style>