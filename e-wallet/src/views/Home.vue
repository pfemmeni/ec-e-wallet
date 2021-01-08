<template>
  <div>
    <Top :element="home"> </Top>
    <Card class="view-choosen" :exCard="choosenCard" v-if="choosenCard"> </Card>
    <button v-if="choosenCard" class="remove-btn " @click="removeCard">
      REMOVE CARD
    </button>

    <CardStack
      :clicked="clicked"
      :choosenCard="choosenCard"
      class="card-stack"
      @showCard="showCard"
    >
    </CardStack>

    <router-link class="anc-btn anc-btn-text" to="add-card"
      >ADD NEW CARD</router-link
    >
  </div>
</template>

<script>
import Top from "../components/Top";
import Card from "../components/Card";
import CardStack from "../components/CardStack";

export default {
  components: { Top, Card, CardStack },
  computed: {
    cardCollection() {
      return this.$root.cardCollection;
    },
  },
  data() {
    return {
      home: { name: "E-WALLET", paragraph: "ACTIVE CARD" },
      choosenCard: null,
      clicked: false,
    };
  },
  methods: {
    showCard(newCard) {
      this.choosenCard = {
        cardNumber: newCard.cardNumber,
        name: newCard.cardholderName,
        month: newCard.month,
        year: newCard.year,
        vendor: newCard.vendor,
        id: newCard.id,
      };
    },
    removeCard() {
      if (confirm("Do you really want to delete?")) {
        this.filterArray(this.choosenCard);
        this.choosenCard = null;
        this.clicked = true;
      }
    },
    filterArray(cardToDelete) {
      this.cardCollection = this.cardCollection.filter(
        (card) => card.id === cardToDelete.id
      );
    },
    // return this.cardCollection.filter(this.choosenCard);
  },
  //   this.$root.cardCollection = this.$root.cardCollection.filter(
  //     this.choosenCard
  //   );
  // }
  // // return this.$root.cardCollection;
};
</script>

<style>
.view-choosen {
  margin-bottom: 0.5rem;
}
.card-stack {
  margin: 2rem 0 12rem;
  display: grid;
  grid-auto-rows: 4rem;
}
.remove-btn {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-pack: center;
  -ms-flex-pack: center;
  justify-content: center;
  -webkit-box-align: center;
  -ms-flex-align: center;
  align-items: center;
  height: 2rem;
  font-size: 1rem;
  text-transform: uppercase;
  font-weight: 700;
  text-decoration: none;
  color: #000;
  border: 0.125rem solid rgb(194, 1, 1);
  -webkit-box-sizing: border-box;
  box-sizing: border-box;
  border-radius: 0.5rem;
  margin-bottom: 2rem 0;
  margin-top: 0;
  background: rgb(240, 126, 126);
  width: 100%;
}
</style>
