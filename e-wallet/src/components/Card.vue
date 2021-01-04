<template>
  <div class="card blank">
    <header>
      <svg
        width="50"
        height="84"
        viewBox="0 0 50 84"
        fill="none"
        xmlns="http://www.w3.org/2000/svg"
      >
        <rect y="44" width="50" height="40" rx="8" fill="#ECE6DF" />
        <line
          y1="56.5"
          x2="18"
          y2="56.5"
          stroke="black"
          stroke-opacity="0.11"
        />
        <line
          x1="33"
          y1="56.5"
          x2="50"
          y2="56.5"
          stroke="black"
          stroke-opacity="0.11"
        />
        <line
          x1="32.5"
          y1="44"
          x2="32.5"
          y2="84"
          stroke="black"
          stroke-opacity="0.11"
        />
        <line
          y1="70.5"
          x2="18"
          y2="70.5"
          stroke="black"
          stroke-opacity="0.11"
        />
        <line
          x1="32"
          y1="70.5"
          x2="50"
          y2="70.5"
          stroke="black"
          stroke-opacity="0.11"
        />
        <line
          x1="18.5"
          y1="44"
          x2="18.5"
          y2="84"
          stroke="black"
          stroke-opacity="0.11"
        />
        <g opacity="0.5">
          <path
            d="M32.8487 26.501C33.5267 27.1657 33.5267 28.2441 32.8487 28.9097C32.1698 29.5753 31.0693 29.5753 30.3913 28.9097C27.4169 25.9941 22.5778 25.9941 19.6038 28.9097C18.9249 29.5753 17.824 29.5753 17.146 28.9097C16.8067 28.5772 16.6378 28.1423 16.6378 27.7049C16.6378 27.2692 16.8072 26.8331 17.146 26.501C21.4756 22.2567 28.5191 22.2567 32.8487 26.501Z"
            fill="black"
          />
          <path
            d="M38.8186 21.073C39.4967 21.7382 39.4967 22.817 38.8186 23.4826C38.1397 24.1482 37.0397 24.1482 36.3612 23.4826C30.0956 17.339 19.9004 17.339 13.6348 23.4826C12.9563 24.1482 11.8554 24.1482 11.1778 23.4826C10.8386 23.15 10.6683 22.7135 10.6683 22.2778C10.6683 21.8412 10.8386 21.406 11.1778 21.073C14.869 17.4538 19.7772 15.4608 24.9978 15.4608C30.2184 15.4608 35.1266 17.4538 38.8186 21.073Z"
            fill="black"
          />
          <path
            d="M44.2866 15.0204C44.965 15.6856 44.965 16.7644 44.2866 17.4296C43.6081 18.0948 42.5081 18.0948 41.8296 17.4296C37.3332 13.0218 31.3554 10.5945 24.9974 10.5945C18.6394 10.5945 12.662 13.0218 8.16651 17.4296C7.48715 18.0948 6.38715 18.0948 5.70911 17.4296C5.36987 17.097 5.20047 16.6609 5.20047 16.2248C5.20047 15.7891 5.37031 15.353 5.70911 15.0204C10.8611 9.96902 17.7119 7.18753 24.9974 7.18753C32.2842 7.18753 39.1346 9.96902 44.2866 15.0204Z"
            fill="black"
          />
        </g>
      </svg>
      <p>{{ exCard.vendor }}</p>
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
</style>
