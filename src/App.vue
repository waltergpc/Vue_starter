<script>
export default {
  name: 'App',
  data() {
    return {
      firstName: 'Bruce',
      lastName: 'Wayne',
      items: [
        {
          id: 1,
          title: 'TV',
          price: 100,
        },
        {
          id: 2,
          title: 'Phone',
          price: 350,
        },
        {
          id: 3,
          title: 'keyboard',
          price: 150,
        },
      ],
      country: '',
    }
  },
  methods: {
    getTotal() {
      return this.items.reduce((total, curr) => (total = total + curr.price), 0)
    },
  },
  computed: {
    fullName() {
      return `${this.firstName} ${this.lastName}`
    },
    total() {
      return this.items.reduce((total, curr) => (total = total + curr.price), 0)
    },
  },
}
</script>

<template>
  <h1>Fullname - {{ firstName }} {{ lastName }}</h1>
  <h1>Computed Fullname - {{ fullName }}</h1>
  <h2>Computed total {{ total }}</h2>
  <h2>Method total {{ getTotal() }}</h2>
  <button @click="items.push({ id: 4, title: 'mouse', price: 50 })">
    Add Item
  </button>
  <input type="text" v-model="country" />
</template>

<style>
@import './assets/base.css';

#app {
  max-width: 1280px;
  margin: 0 auto;
  padding: 2rem;

  font-weight: normal;
}

header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

a,
.green {
  text-decoration: none;
  color: hsla(160, 100%, 37%, 1);
  transition: 0.4s;
}

@media (hover: hover) {
  a:hover {
    background-color: hsla(160, 100%, 37%, 0.2);
  }
}

@media (min-width: 1024px) {
  body {
    display: flex;
    place-items: center;
  }

  #app {
    display: grid;
    grid-template-columns: 1fr 1fr;
    padding: 0 2rem;
  }

  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  .logo {
    margin: 0 2rem 0 0;
  }
}
</style>
