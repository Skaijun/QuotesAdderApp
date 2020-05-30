<template>
  <section class="quote-add">
    <form class="add__form">
      <label class="add__form-label">Write new quote:</label>
      <textarea
        class="add_form-textarea"
        placeholder="Type your quote..."
        name="quote"
        cols="30"
        rows="6"
        v-model="quote"
        @keyup.enter.prevent="addNewQuote"
      ></textarea>
      <button class="add__form-btn" @click.prevent="addNewQuote">Add Quote</button>
    </form>
  </section>
</template>

<script>
export default {
  props: ["quotesQuantity"],
  data: function() {
    return {
      quote: ""
    };
  },
  methods: {
    addNewQuote() {
      if (this.quote === "") {
        alert("You have to write down the quote first!");
      } else {
        if (this.quotesQuantity < 9) {
          this.$emit("addedNewQuote", this.quote);
          this.quote = "";
        } else {
          alert("Please, remove the Quotes first;)");
        }
      }
    }
  }
};
</script>

<style scoped>
.quote-add {
  margin: 25px auto;
}
.add__form {
  display: flex;
  flex-wrap: wrap;
}
.add__form-label {
  font-size: 20px;
  line-height: 26px;
  margin-bottom: 5px;
  font-weight: 900;
}
.add_form-textarea {
  width: 1230px;
  font-size: 18px;
  line-height: 22px;
  font-family: "Chelsea Market", sans-serif;
  padding: 12px;
  display: inline-block;
  border-top-left-radius: 5px;
  border-top-right-radius: 5px;
  border: none;
  outline: none;
  resize: none;
}
.add__form-btn {
  width: 100%;
  padding: 10px;
  background-color: darkblue;
  color: white;
  font-size: 18px;
  line-height: 22px;
  cursor: pointer;
  outline: none;
  border: none;
  border-bottom-left-radius: 5px;
  border-bottom-right-radius: 5px;
  transition: all 0.8s ease;
}
.add__form-btn:hover {
  background-color: cornflowerblue;
  color: black;
}
</style>
