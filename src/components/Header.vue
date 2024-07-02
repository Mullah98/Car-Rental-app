<template>
    <div class="header-page">
      <div class="text-container">
        <h1>{{ title }}</h1>
        <p>"{{ slogan }}"</p>
    </div>
      <img :src="Car" alt="car">
    </div>
</template>

<script>
import car from '../assets/red-car.jpg'

    export default {
        name: 'HeaderComponent',
        data() {
            return {
                title: 'Elite Car Rental',
                slogan: 'Luxury on demand, delivered',
                Car: car,
            }
        }
    }
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Raleway:ital,wght@0,100..900;1,100..900&display=swap');

.text-container {
    position: relative;
    display: block;
    flex-direction: column;
    z-index: 1;
}

h1 {
    color: rgb(15, 15, 155);
    font-size: 10em;
    font-family: "Raleway", sans-serif;
    font-weight: 900;
    font-style: italic;
    letter-spacing: 5px;
}

p {
    font-size: 3em;
    font-family:Arial, Helvetica, sans-serif;
    font-style: italic;
    font-weight: 800;
    margin-top: -1em;
}

img {
    width: 50%;
    max-width: 100%;
    height: auto;
    margin-top: -10em;
    z-index: -1;
}
</style>