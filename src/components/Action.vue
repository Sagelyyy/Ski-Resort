<script>
export default {
  data() {
    return {
      currentHover: null,
      items: [
        {
          id: 0,
          image:
            "https://images.unsplash.com/photo-1551698618-1dfe5d97d256?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MTd8fHNsb3clMjBza2l8ZW58MHx8MHx8fDA%3D",
          alt: "a skiier going down a mountain",
          description: "Carve fresh powder like a pro down our endless slopes.",
        },
        {
          id: 1,
          image:
            "https://images.unsplash.com/photo-1488580923008-6f98dfbd7a25?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
          alt: "a snowboarder on a mountain",
          description:
            "Feel the adrenaline rush as you catch epic air and leave a trail of powder in your wake.",
        },
        {
          id: 2,
          image:
            "https://images.unsplash.com/photo-1529669851596-ba9a5549af95?q=80&w=1932&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
          alt: "a snowboarder standing on a tall mountain",
          description:
            "Soak in the breathtaking mountain vistas and conquer new heights - your winter wonderland awaits.",
        },
      ],
    };
  },
  methods: {
    setHover(id) {
      return (this.currentHover = id);
    },
  },
};
</script>

<template>
  <section>
    <div>
      <h3 class="text-center text-3xl p-10">Explore the possibilities.</h3>
    </div>
    <div class="grid lg:grid-cols-3 gap-8 mb-4" id="items">
      <div
        class="relative cursor-pointer"
        v-for="item in items"
        :key="item.id"
        @mouseenter="setHover(item.id)"
        @touchstart="setHover(item.id)"
        @mouseleave="setHover(null)"
      >
        <img class="w-full rounded-2xl" :src="item.image" :alt="item.alt" />
        <div
          class="absolute top-0 left-0 bg-black/25 w-full h-full rounded-2xl p-2 font-headline text-2xl"
          v-show="currentHover === item.id"
        >
          <p class="text-slate-100">{{ item.description }}</p>
        </div>
      </div>
    </div>
  </section>
</template>
