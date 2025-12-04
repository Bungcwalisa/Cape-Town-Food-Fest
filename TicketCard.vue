<script setup>

defineProps({
  title: { type: String, required: true },
  price: { type: String, required: true },
  perks: { type: Array, default: () => [] },
  highlight: { type: Boolean, default: false }
})
</script>

<TicketCard
  title="Day Pass"
  price="R199"
  :perks="['Valid 1 Day', 'All Food Zones', 'Live Performances']"
/>

<TicketCard
  title="Weekend Pass"
  price="R499"
  :perks="['All 3 Days', 'VIP Lounge Access', 'Priority Entry']"
  :highlight="true"
/>

<template>
  <div class="ticket-card" :class="{ highlight }">
    <h3 class="ticket-title">{{ title }}</h3>
    <p class="ticket-price">{{ price }}</p>

    <ul class="ticket-perks">
      <li v-for="perk in perks" :key="perk">✔ {{ perk }}</li>
    </ul>

    <button class="btn buy-btn">Buy Ticket</button>
  </div>
</template>

<style scoped>
.ticket-card {
  background: #fff;
  padding: 1.8rem;
  border-radius: 16px;
  border: 2px solid #eee;
  box-shadow: 0 4px 14px rgba(0,0,0,0.06);
  transition: 0.3s ease;
  text-align: center;
}

.ticket-card:hover {
  transform: translateY(-6px);
  border-color: #ff6b00;
}

.ticket-card.highlight {
  border-color: #ff6b00;
  box-shadow: 0 6px 20px rgba(255,107,0,0.25);
  transform: scale(1.02);
}

.ticket-title {
  font-size: 1.4rem;
  font-weight: 700;
  margin-bottom: 0.5rem;
}

.ticket-price {
  font-size: 2rem;
  font-weight: 900;
  color: #ff6b00;
  margin-bottom: 1rem;
}

.ticket-perks {
  list-style: none;
  padding: 0;
  margin: 0 0 1.5rem 0;
  font-size: 0.95rem;
}

.ticket-perks li {
  margin: 0.3rem 0;
}

.buy-btn {
  background: #ff6b00;
  color: white;
  padding: 0.7rem 1.4rem;
  border-radius: 10px;
  font-weight: 700;
  cursor: pointer;
  transition: 0.3s ease;
  border: none;
}

.buy-btn:hover {
  background: #e55e00;
}
</style>