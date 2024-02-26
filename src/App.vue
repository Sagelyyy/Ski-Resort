<script>
import Hero from "./components/Hero.vue";
import Action from "./components/Action.vue";
import Cta from "./components/Cta.vue";
import Tickets from "./components/Tickets.vue";
export default {
  components: { Hero, Action, Cta, Tickets },
};
</script>

<template>
  <Hero />
  <Action />
  <Cta />
  <Tickets />
</template>
