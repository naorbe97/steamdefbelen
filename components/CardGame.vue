<template>
    <div class="card">
      <img src="/imagen_juego.jpg" alt="Imagen del juego" class="card-img">
      <div class="card-body">
        <h2 class="card-title">Nombre del Juego</h2>
        <p class="card-price">$49.99</p>
        <button class="btn-buy">Comprar</button>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'GameCard'
  }
  </script>
  
  <style scoped>
  .card {
    border: 1px solid #ddd;
    border-radius: 5px;
    overflow: hidden;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
    width: 300px;
  }
  
  .card-img {
    width: 100%;
    height: auto;
  }
  
  .card-body {
    padding: 20px;
  }
  
  .card-title {
    font-size: 18px;
    margin: 0;
  }
  
  .card-price {
    font-size: 16px;
    margin: 10px 0;
  }
  
  .btn-buy {
    background-color: #007bff;
    color: #fff;
    border: none;
    cursor: pointer;
    padding: 10px 20px;
    border-radius: 5px;
    font-size: 16px;
  }
  
  .btn-buy:hover {
    background-color: #0056b3;
  }
  </style>