<template>
  <div>
    <Top :element="home"> </Top>
    <Card :exCard="exampleCard"> </Card>
    <CardStack></CardStack>
    <button class="anc-btn">
      <router-link class="anc-btn-text" to="add-card">ADD NEW CARD</router-link>
    </button>
  </div>
</template>

<script>
import Top from "../components/Top";
import Card from "../components/Card";
import CardStack from "../components/CardStack";
export default {
  components: { Top, Card, CardStack },
  data() {
    return {
      home: { name: "E-WALLET", paragraph: "ACTIVE CARD" },
      exampleCard: {
        cardNumber: "XXXX XXXX XXXX XXXX",
        name: "Anna Karlsson",
        month: "03",
        year: "23",
      },
    };
  },
};
</script>

<style></style>
