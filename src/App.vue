<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/r.png" class="logo" />
    <h1>WELCOME TO R' SPACE</h1>

    <!-- Box Color Changer -->
    <section class="color-changer-section">
      <h2>Box Color Changer</h2>
      <div class="color-buttons">
        <button @click="changeBoxColor('#F6C10D')">Mustard</button>
        <button @click="changeBoxColor('#4CAF50')">Green</button>
        <button @click="changeBoxColor('#2196F3')">Blue</button>
      </div>
      <div class="color-box" :style="{ backgroundColor: boxColor }"></div>
    </section>

    <!-- Click Counter -->
    <section class="counter-section">
      <h2>Click Counter</h2>
      <button @click="incrementCounter" class="counter-button">Click Me</button>
      <p class="counter-display">Clicked <span>{{ counter }}</span> times.</p>
    </section>

    <!-- Image Carousel -->
    <section class="carousel-section">
      <h2>Image Carousel</h2>
      <div class="carousel">
        <img :src="images[currentImage]" alt="Carousel Image" />
        <div class="carousel-buttons">
          <button @click="prevImage">Prev</button>
          <button @click="nextImage">Next</button>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
import image1 from '@/assets/gng.jpg';
import image2 from '@/assets/terjun.jpg';
import image3 from '@/assets/download (4).jpeg';

export default {
  name: 'App',
  data() {
    return {
      counter: 0,
      boxColor: '#F6C10D', // Default box color
      images: [image1, image2, image3],
      currentImage: 0
    };
  },
  methods: {
    incrementCounter() {
      this.counter++;
    },
    changeBoxColor(color) {
      this.boxColor = color;
    },
    prevImage() {
      this.currentImage = (this.currentImage - 1 + this.images.length) % this.images.length;
    },
    nextImage() {
      this.currentImage = (this.currentImage + 1) % this.images.length;
    }
  }
};
</script>

<style>
:root {
  --app-background-color: #8CB9BD; /* Teal background color */
}

html, body {
  margin: 0;
  padding: 0;
  width: 100%;
  height: 100%;
  background-color: var(--app-background-color); /* Full-screen background color */
}

#app {
  font-family: Helvetica, Arial, sans-serif;
  text-align: center;
  color: #333;
  margin: 0 auto;
  padding: 20px;
  max-width: 600px;
  border-radius: 20px; /* Increased border radius */
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  background-color: #FFFFFF;
  min-height: 100vh; /* Ensure it stretches to full height */
}

h1, h2 {
  color: #333;
}

.logo {
  max-width: 150px;
  margin-bottom: 20px;
}

section {
  margin: 20px 0;
  padding: 20px;
  border-radius: 50px;
  background-color: #FFFFFF;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  color: #333;
}

.color-changer-section {
  margin: 20px 0;
}

.color-buttons button {
  margin: 5px;
  padding: 10px 15px;
  background-color: #B67352;
  border: none;
  color: #ffffff;
  font-size: 14px;
  cursor: pointer;
  transition: background-color 0.3s, transform 0.2s;
  border-radius: 18px;
}

.color-box {
  width: 100px;
  height: 100px;
  margin: 20px auto;
  border-radius: 15px;
}

.counter-section,
.carousel-section {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.counter-button {
  background-color: #ECB159;
  border: none;
  color: #ffffff;
  padding: 15px 25px;
  font-size: 16px;
  font-weight: bold;
  border-radius: 50px;
  cursor: pointer;
  transition: transform 0.2s, box-shadow 0.2s;
  box-shadow: 0 6px 10px rgba(0, 0, 0, 0.1);
  margin-bottom: 10px;
}

.counter-button:hover {
  transform: translateY(-3px);
  box-shadow: 0 10px 15px rgba(0, 0, 0, 0.2);
}

.counter-display {
  font-size: 20px;
  font-weight: bold;
  color: #333;
  margin-top: 10px;
}

.counter-display span {
  color: #ECB159;
  font-size: 24px;
}

.carousel {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-bottom: 10px;
}

.carousel img {
  max-width: 100%;
  border: none;
  border-radius: 20px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  margin-bottom: 10px;
}

.carousel-buttons button {
  margin: 5px;
  padding: 10px 15px;
  background-color: #B67352;
  border: none;
  color: #ffffff;
  font-size: 14px;
  cursor: pointer;
  transition: background-color 0.3s, transform 0.2s;
  border-radius: 18px;
}

button:hover {
  background-color: #ECB159;
  transform: scale(1.05);
}
</style>
