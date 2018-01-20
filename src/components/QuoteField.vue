<template>
  <div class="quote-field">
    <h3>Quote</h3>
    <div class="quote-field__inner">
      <textarea cols="30"
                rows="10" v-model="textAreaValue"></textarea>
      <button class="quote-field__button"
              @click="addQuote">Add Quote</button>
    </div>
  </div>
</template>

<script>
  export default {
    props: {
      quotesStatus: {
        type: Object,
        required: true
      }
    },
    data() {
      return {
        textAreaValue: ''
      };
    },
    methods: {
      addQuote() {
        if (this.increaseLine() ) {
          this.$emit('addNewQuote', this.textAreaValue);
          this.textAreaValue = '';
        }
      },
      increaseLine() {
        if (this.quotesStatus.addedQuotes < this.quotesStatus.maxQuotes) {
          this.quotesStatus.addedQuotes++;
          return true;
        } else {
          alert(`максимально, можно добавить только ${ this.quotesStatus.maxQuotes } цитат`);
          return false;
        }
      }
    }
  }
</script>

<style lang="scss">
  .quote-field {
    width: 600px;
    margin: 60px auto;
    text-align: center;
    
    &__button {
      display: block;
      margin: 0 auto;
      border: none;
      padding: 10px;
      border-radius: 6px;
      font-weight: bold;
      background-color: cornflowerblue;
      color: white;
      font-size: 15px;
      cursor: pointer;
      
      &:hover {
        color: #000;
        transition: 400ms;
      }
    }
    
    textarea {
      -webkit-box-shadow: inset 2px 2px 2px 0px #dddddd;
      -moz-box-shadow: inset 2px 2px 2px 0px #dddddd;
      box-shadow: inset 2px 2px 2px 0px #dddddd;
      overflow: auto;
      padding: 7px 10px;
      width: 100%;
      resize: none;
      font-size: 13px;
      border: 1px solid #aaa;
      margin-bottom: 10px;
    }

    h3 {
      text-align: left;
      margin-bottom: 10px;
    }
    
  }
</style>