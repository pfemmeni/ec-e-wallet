<template>
  <form autocomplete="off" v-on:submit.prevent class="card-form">
    <label for="number" class="col-2">Card Nummer</label>
    <input
      type="text"
      maxlength="16"
      placeholder="XXXX XXXX XXXX XXXX"
      class="col-2"
      name="number"
      v-model="newCard.enteredCardNumber"
      @input="$emit('newCardEx', newCard)"
    />
    <label for="cardholder" class="col-2">Cardholder Name</label>
    <input
      type="text"
      placeholder="Firstname Lastname "
      class="col-2"
      name="name"
      v-model="newCard.enteredCardholderName"
      @input="$emit('newCardEx', newCard)"
    />
    <label for="month" class="col-1">Month </label>
    <label for="year" class="col-1">Year</label>
    <select
      name="month"
      class="col-1"
      v-model="newCard.enteredMonth"
      @change="$emit('newCardEx', newCard)"
    >
      <option value="1">1</option>
      <option value="2">2</option>
      <option value="3">3</option>
      <option value="4">4</option>
      <option value="5">5</option>
      <option value="6">6</option>
      <option value="7">7</option>
      <option value="8">8</option>
      <option value="9">9</option>
      <option value="10">10</option>
      <option value="11">11</option>
      <option value="12">12</option>
    </select>
    <select
      name="year"
      class="col-1"
      @change="$emit('newCardEx', newCard)"
      v-model="newCard.enteredYear"
    >
      <option value="22">22</option>
      <option value="23">23</option>
      <option value="24">24</option>
      <option value="25">25</option>
    </select>
    <label for="vendor" class="col-2">Vendor</label>
    <select
      name="vendor"
      class="col-2"
      v-model="newCard.enteredVendor"
      @change="$emit('newCardEx', newCard)"
    >
      <option value="bitcoin">Bitcoin</option>
      <option value="blockchain">Blockchain</option>
      <option value="ninja">Ninja</option>
      <option value="evil">Evil</option>
    </select>
  </form>
</template>

<script>
export default {
  data() {
    return {
      newCard: {
        enteredCardNumber: "",
        enteredCardholderName: "",
        enteredMonth: "",
        enteredYear: "",
        enteredVendor: "",
        id: Date.now(),
      },
    };
  },
};
</script>

<style>
.card-form {
  margin: 1rem 0 0;
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 0 1rem;
}
.col-1 {
  grid-column: auto/span 1;
  grid-column-start: auto;
  grid-column-end: span 1;
}
.col-2 {
  grid-column: auto/span 2;
  grid-column-start: auto;
  grid-column-end: span 2;
}
.card-form label {
  padding: 0.25rem 0;
  font-size: 0.7rem;
  text-transform: uppercase;
}

.card-form input,
select {
  border: 1px solid #000;
  border-radius: 0.25rem;
  padding: 0.5rem;
  height: 2.6rem;
  margin: 0 0 0.8rem;
  -webkit-box-sizing: border-box;
  box-sizing: border-box;
  font-size: 1rem;
  width: 100%;
}
input[type="text" i] {
  padding: 1px 2px;
}
input {
  -webkit-writing-mode: horizontal-tb !important;
  text-rendering: auto;
  color: -internal-light-dark(black, white);
  letter-spacing: normal;
  word-spacing: normal;
  text-transform: none;
  text-indent: 0px;
  text-shadow: none;
  display: inline-block;
  text-align: start;
  appearance: textfield;
  background-color: -internal-light-dark(rgb(255, 255, 255), rgb(59, 59, 59));
  -webkit-rtl-ordering: logical;
  cursor: text;
  margin: 0em;
  font: 400 13.3333px Arial;
  padding: 1px 2px;
  border-width: 2px;
  border-style: inset;
  border-color: -internal-light-dark(rgb(118, 118, 118), rgb(133, 133, 133));
  border-image: initial;
}
select:not(:-internal-list-box) {
  overflow: visible !important;
}
select {
  -webkit-writing-mode: horizontal-tb !important;
  text-rendering: auto;
  color: -internal-light-dark(black, white);
  letter-spacing: normal;
  word-spacing: normal;
  text-transform: none;
  text-indent: 0px;
  text-shadow: none;
  display: inline-block;
  text-align: start;
  appearance: menulist;
  box-sizing: border-box;
  align-items: center;
  white-space: pre;
  -webkit-rtl-ordering: logical;
  background-color: -internal-light-dark(rgb(255, 255, 255), rgb(59, 59, 59));
  cursor: default;
  margin: 0em;
  font: 400 13.3333px Arial;
  border-radius: 0.25rem;
  border-width: 1px;
  border-style: solid;
  border-color: -internal-light-dark(rgb(118, 118, 118), rgb(133, 133, 133));
  border-image: initial;
}
</style>
