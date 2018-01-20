<template>
  <div class="quotes">
    <status-bar :quotesStatus="quotesStatus"></status-bar>
    <quote-field :quotesStatus="quotesStatus" @addNewQuote="addNewQuote({ text: $event })"></quote-field>
    <quotes :quotesText="quotesText"
            :quotesStatus="quotesStatus"
            @quoteTextForDelete="deleteQuote($event)"></quotes>
    <tips></tips>
  </div>
</template>

<script>
  import StatusBar from './StatusBar.vue';
  import QuoteField from './QuoteField.vue';
  import Quotes from './Quotes.vue';
  import Tips from './Tips.vue';

  export default {
    components: {
      StatusBar,
      QuoteField,
      Quotes,
      Tips
    },
    data(){
      return {
        quotesStatus: {
          maxQuotes: 10,
          addedQuotes: 1
        },
        quotesText: [
          { text: 'Success is the child of audacity' }
        ]
      }
    },
    methods: {
      addNewQuote(oneTextFieldObj) {
        return this.quotesText.unshift(oneTextFieldObj);
      },
      deleteQuote(quote) {
        this.quotesText.splice(quote, 1);

      }
    }
  }
</script>

<style scoped>

</style>