<template>
  <main>
    <Top :element="header"> </Top>
    <Card :exCard="exampleCard"></Card>
    <p class="error" v-if="error">Fill all information</p>
    <CardForm @newCardEx="addExampleCard"></CardForm>
    <button class="anc-btn anc-btn-text button" @click="newCardAdd">
      ADD CARD
    </button>
  </main>
</template>

<script>
import Top from "../components/Top";
import Card from "../components/Card";
import CardForm from "../components/CardForm";

export default {
  components: { Top, Card, CardForm },
  data() {
    return {
      header: { name: "ADD NEW CARD", paragraph: "NEW CARD" },
      exampleCard: {},
      error: false,
    };
  },

  methods: {
    addExampleCard(newCard) {
      this.exampleCard = {
        cardNumber: newCard.enteredCardNumber,
        name: newCard.enteredCardholderName,
        month: newCard.enteredMonth,
        year: newCard.enteredYear,
        vendor: newCard.enteredVendor,
        id: newCard.id,
      };
    },
    newCardAdd() {
      if (
        !this.exampleCard.cardNumber ||
        !this.exampleCard.name ||
        !this.exampleCard.month ||
        !this.exampleCard.year ||
        !this.exampleCard.vendor
      ) {
        this.error = true;
      } else {
        this.$root.cardCollection.push(this.exampleCard);
        this.$router.push("/");
      }
    },
  },
};
</script>

<style>
.error {
  margin-top: 2rem;

  font-weight: 600;
  color: red;
  display: flex;
  justify-content: center;
}
.anc-btn {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-pack: center;
  -ms-flex-pack: center;
  justify-content: center;
  -webkit-box-align: center;
  -ms-flex-align: center;
  align-items: center;
  height: 4rem;
  font-size: 1.2rem;
  text-transform: uppercase;
  font-weight: 700;
  text-decoration: none;
  color: #000;
  border: 0.125rem solid #000;
  -webkit-box-sizing: border-box;
  box-sizing: border-box;
  border-radius: 0.5rem;
  margin: 2rem 0;
  background: #fff;
  width: 100%;
}

.anc-btn-text {
  font-size: 1.2rem;
  text-transform: uppercase;
  font-weight: 700;
  text-decoration: none;
  color: #000;
  background: #fff;
}
</style>
