<template>
  <div>
    <Card
      v-for="oneCard in cardCollection"
      :key="oneCard.id"
      :exCard="oneCard"
      @click="$emit('showCard', oneCard)"
    ></Card>
  </div>
</template>

<script>
import Card from "../components/Card";
export default {
  components: { Card },

  computed: {
    cardCollection() {
      return this.$root.cardCollection;
    },
  },
};
</script>

<style scoped></style>
