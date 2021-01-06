<template>
  <div class="card blank" @click="$emit('click')" :class="exCard.vendor">
    <header>
      <img src="../assets/chip-dark.svg" alt="chip" />
      <img
        v-if="exCard.vendor"
        :src="require('../assets/vendor-' + exCard.vendor + '.svg')"
        alt="vendor"
      />
    </header>
    <section class="number">
      {{ exCard.cardNumber }}
    </section>
    <section class="info">
      <aside class="holder">
        <span>CARDHOLDER NAME</span>
        <p>{{ exCard.name }}</p>
      </aside>
      <aside>
        <span>MM/YY</span>
        <p>{{ exCard.month }}/{{ exCard.year }}</p>
      </aside>
    </section>
  </div>
</template>

<script>
export default {
  props: {
    exCard: Object,
  },
};
</script>

<style>
.blank {
  background: linear-gradient(
      237.75deg,
      hsla(0, 0%, 100%, 0.24),
      hsla(0, 0%, 100%, 0)
    ),
    #d0d0d0;
}

.card {
  max-width: 24rem;
  height: 14rem;
  border-radius: 0.6rem;
  background: #eee;
  padding: 1rem;
  -webkit-box-sizing: border-box;
  box-sizing: border-box;
  -webkit-box-shadow: 0 0 0.5rem rgba(0, 0, 0, 0.4);
  box-shadow: 0 0 0.5rem rgba(0, 0, 0, 0.4);
  display: grid;
  gap: 0.5rem 0;
  grid-template-columns: 1fr 1fr;
  grid-auto-rows: 2.8rem;
  text-shadow: -1px -1px 2px hsla(0, 0%, 100%, 0.4);
}

.card header {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  grid-column: auto/span 2;
  grid-row: auto/span 2;
  -webkit-box-pack: justify;
  -ms-flex-pack: justify;
  justify-content: space-between;
  -webkit-box-align: start;
  -ms-flex-align: start;
  align-items: flex-start;
}
.card section.info,
.card section.number {
  grid-column: auto/span 2;
  grid-row: auto/span 1;
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
}

.card section.number {
  font-size: 1.6rem;
  letter-spacing: 0.05rem;
  padding: 0.5rem 0 0;
  text-transform: uppercase;
}
.card section.info aside.holder {
  -webkit-box-flex: 1;
  -ms-flex: 1;
  flex: 1;
}
.card section.info aside.holder {
  -webkit-box-flex: 1;
  -ms-flex: 1;
  flex: 1;
}
aside {
  display: block;
}
.card section aside span {
  display: block;
  text-transform: uppercase;
  font-size: 0.7rem;
  margin: 0 0 0.25rem;
}
p {
  display: block;
  text-transform: uppercase;

  margin: 0 0 0.25rem;
}

.bitcoin {
  background-color: #eee;
}

.blockchain {
  background-color: rgb(48, 48, 180);
  color: #fff;
}
.ninja {
  background-color: rgb(43, 151, 43);
  color: #fff;
}
.evil {
  background-color: rgb(185, 2, 2);
  color: #fff;
}
</style>
