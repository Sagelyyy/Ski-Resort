<script>
export default {
  data() {
    return {
      tickets: [
        { type: "General", quantity: 0 },
        { type: "VIP", quantity: 0 },
        { type: "Premium", quantity: 0 },
      ],
      cart: [],
    };
  },
  methods: {
    incrementTicket(index) {
      this.tickets[index].quantity++;
    },
    decrementTicket(index) {
      if (this.tickets[index].quantity > 0) {
        this.tickets[index].quantity--;
      }
    },
    addToCart() {
      this.cart = this.tickets.filter((ticket) => ticket.quantity > 0);
    },
  },
};
</script>

<template>
  <div class="container mx-auto p-4 grid grid-cols-2 items-center">
    <div>
      <div
        v-for="(ticket, index) in tickets"
        :key="index"
        class="mb-4 flex items-center"
      >
        <h3 class="text-lg font-semibold mr-4">{{ ticket.type }}</h3>
        <div class="flex items-center">
          <button
            @click="incrementTicket(index)"
            class="px-3 py-1 bg-blue-500 text-white rounded-md"
          >
            +
          </button>
          <p class="mx-4">{{ ticket.quantity }}</p>
          <button
            @click="decrementTicket(index)"
            class="px-3 py-1 bg-red-500 text-white rounded-md"
          >
            -
          </button>
        </div>
      </div>
      <button
        @click="addToCart"
        class="bg-green-500 text-white px-4 py-2 rounded-md mb-4"
      >
        Add to Cart
      </button>
    </div>
    <div v-show="cart">
      <h2 class="text-xl font-semibold mb-2">Cart</h2>
      <ul>
        <li v-for="(ticket, index) in cart" :key="index" class="mb-2">
          <span class="font-semibold">{{ ticket.type }}</span> - Quantity:
          {{ ticket.quantity }}
        </li>
      </ul>
    </div>
  </div>
</template>
