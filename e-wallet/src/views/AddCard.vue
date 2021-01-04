<template>
  <main>
    <Top :element="header"> </Top>
    <Card :exCard="exampleCard"></Card>
    <CardForm @newCardEx="addExampleCard"></CardForm>
    <button class="anc-btn" @click="newCardAdd">
      <!-- <router-link class="anc-btn-text" to="/">ADD CARD</router-link> -->
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
      cardCollection: [],
      exampleCard: {},
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
      };
    },
    newCardAdd() {
      this.cardCollection.push(this.exampleCard);
    },
  },
};
</script>

<style>
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
