<template>
    <div class="card-grid">
      <div
        v-for="card in cards"
        :key="card.id"
        class="flip-card"
        @click="flipCard(card.id)"
      >
        <div class="flip-card-inner" :class="{ flipped: card.flipped }">
          <!-- Front Side -->
          <div class="flip-card-front">
            <Card>
              <template #title>{{ card.title }}</template>
              <template #content>
                <p>{{ card.frontContent }}</p>
              </template>
            </Card>
          </div>
          <!-- Back Side -->
          <div class="flip-card-back">
            <Card>
              <template #title>{{ card.title }}</template>
              <template #content>
                <p>{{ card.backContent }}</p>
              </template>
            </Card>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  import { ref } from 'vue';
  import Card from 'primevue/card';
  
  export default {
    name: 'FlipCardGrid',
    components: { Card },
    setup() {
      const cards = ref([
        { id: 1, title: 'Card 1', frontContent: 'Front of Card 1', backContent: 'Back of Card 1', flipped: false },
        { id: 2, title: 'Card 2', frontContent: 'Front of Card 2', backContent: 'Back of Card 2', flipped: false },
        { id: 3, title: 'Card 3', frontContent: 'Front of Card 3', backContent: 'Back of Card 3', flipped: false },
        { id: 4, title: 'Card 4', frontContent: 'Front of Card 4', backContent: 'Back of Card 4', flipped: false },
        { id: 5, title: 'Card 5', frontContent: 'Front of Card 5', backContent: 'Back of Card 5', flipped: false },
        { id: 6, title: 'Card 6', frontContent: 'Front of Card 6', backContent: 'Back of Card 6', flipped: false },
        { id: 7, title: 'Card 7', frontContent: 'Front of Card 7', backContent: 'Back of Card 7', flipped: false },
        { id: 8, title: 'Card 8', frontContent: 'Front of Card 8', backContent: 'Back of Card 8', flipped: false },
      ]);
  
      function flipCard(id) {
        const card = cards.value.find(c => c.id === id);
        if (card) {
          card.flipped = !card.flipped;
        }
      }
  
      return { cards, flipCard };
    },
  };
  </script>
  
  <style scoped>
  .card-grid {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 1rem;
  }
  
  .flip-card {
    perspective: 1000px;
    cursor: pointer;
  }
  
  .flip-card-inner {
    position: relative;
    width: 100%;
    height: 200px;
    transition: transform 0.6s;
    transform-style: preserve-3d;
  }
  
  .flip-card-inner.flipped {
    transform: rotateY(180deg);
  }
  
  .flip-card-front,
  .flip-card-back {
    position: absolute;
    width: 100%;
    height: 100%;
    backface-visibility: hidden;
  }
  
  .flip-card-back {
    transform: rotateY(180deg);
  }
  </style>
  