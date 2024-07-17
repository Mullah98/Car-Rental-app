<template>
    <div class="header-page">
      <div class="text-container">
        <h1>{{ title }}</h1>
        <p>"{{ slogan }}"</p>
    </div>
    <div v-motion-slide-visible-right>
      <img :src="Car" alt="car">
      </div>
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

@media only screen and (max-width: 767px) {
    h1 {
        white-space: break-spaces;
        font-size: 8em;
        margin: 0.6em 0 0 0.5em;
    }

    p {
        white-space: pre-line;
        margin: 1em 0 0 2.5em;
    }

    img {
        width: 100%;;
        max-width: 100%;
        margin: 1em 0 0 0;
    }
}
</style>