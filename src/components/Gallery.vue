<script setup>
import leatherJacket from '../assets/leather-jacket.jpg'
import denimJacket from '../assets/denim-jacket.jpg'
import bomberJacket from '../assets/bomber-jacket.jpg'
</script>

<template>
    <h1>{{ msg }}</h1>
    <div class="row">
      <div class="column">
        <p>Classic Leather Jacket</p>
        <img :src="leatherJacket" alt="Classic Leather Jacket" />
      </div>
      <div class="column">
        <p>Denim Jacket</p>
        <img :src="denimJacket" alt="Denim Jacket" />
      </div>
    </div>
    <div class="row">
      <div class="column">
        <p>Bomber Jacket</p>
        <img :src="bomberJacket" alt="Bomber Jacket" />
      </div>
      <div class="column">
        <p>Winter Puffer Jacket</p>
        <img src="puffer-jacket.jpg" alt="Winter Puffer Jacket" />
      </div>
    </div>
  </template>
  
  <style scoped>
  .row {
    display: flex;
    flex-wrap: wrap;
    padding: 0 4px;
    margin-bottom: 20px;
  }
  
  .column {
    flex: 50%;
    padding: 0 4px;
    text-align: center;
  }
  
  img {
    display: block;
    margin: 0 auto;
    width: 300px;
    height: auto;
    border-radius: 8px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    transition: transform 0.3s ease;
  }
  
  img:hover {
    transform: scale(1.05);
  }
  
  p {
    margin: 10px 0;
    font-size: 1.2em;
    color: #333;
  }
  
  h1 {
    text-align: center;
    color: #2c3e50;
    margin-bottom: 30px;
  }
  </style>