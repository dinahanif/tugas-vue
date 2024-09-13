<template>
  <div id="app">
    <!-- Click Counter -->
    <div class="counter">
      <h2>Click Counter</h2>
      <p>Count: {{ count }}</p>
      <button @click="incrementCount">Increment</button>
    </div>

    <!-- Box Color Changer -->
    <div class="container center-color-changer">
      <h2>Box Color Changer</h2>
      <div :style="{ backgroundColor: boxColor }" class="color-box"></div>
      <button @click="changeColor">Change Color</button>
    </div>

    <!-- Image Carousel -->
    <div class="container mt-5">
      <h2>Image Carousel</h2>
      <img :src="images[currentImage]" class="carousel-image" />
      <button @click="prevImage">Previous</button>
      <button @click="nextImage">Next</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      // Data untuk Click Counter
      count: 0,

      // Data untuk Box Color Changer
      boxColor: 'red',
      colors: ['red', 'blue', 'green', 'yellow', 'purple'],

      // Data untuk Image Carousel
      images: [
        'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTyBZBspYRy9VF3NKWKKCpw13MjtjvkAQbLpUzSIo0wCz7Swl6hjoLsvACP1sbOnbwgJnc&usqp=CAU',
        'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQ8xo018rvfvDD0-jqG0C4MANO4ywvdl59TS15k0wAm0IaQr40lTvHZcWq-eJN3l0q1wZk&usqp=CAU',
        'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRb-ETNhqVe3izFl1b42PWBpPjav2aUm7an7RZEdnPANWaDKQjPpTpoo4l-p2cj29Ei38M&usqp=CAU'
      ],
      currentImage: 0
    };
  },
  methods: {
    // Method untuk Click Counter
    incrementCount() {
      this.count++;
    },

    // Method untuk Box Color Changer
    changeColor() {
      const randomIndex = Math.floor(Math.random() * this.colors.length);
      this.boxColor = this.colors[randomIndex];
    },

    // Method untuk Image Carousel
    prevImage() {
      this.currentImage =
        this.currentImage === 0 ? this.images.length - 1 : this.currentImage - 1;
    },
    nextImage() {
      this.currentImage =
        this.currentImage === this.images.length - 1 ? 0 : this.currentImage + 1;
    }
  }
};
</script>

<style scoped>
#app {
  text-align: center;
}

.counter {
  margin: 20px;
}

.color-box {
  width: 200px;
  height: 200px;
  margin: 20px auto;
}

.carousel {
  margin-top: 20px;
}

.carousel-image {
  width: 300px;
  height: 200px;
  display: block;
  margin: 0 auto;
}
</style>
