<template>
<div class="order-page">
    <h2 v-motion-slide-visible-left>Explore our diverse range of premium vehicles</h2>
    <div class="car-grid" v-motion-slide-visible-right>
        <div v-for="(car, i) in CarCollection" :key="i">
            <div class="car-item">
                <img :src="car.image" alt="Car Image" class="car-img">
                <h3>{{ car.year }} {{ car.make }} {{ car.model }}</h3><hr>
                <h4>{{ car.engine }}</h4>
                <h4>BHP: {{ car.power }}</h4><hr>
                <button @click="openModal(car)">Hire now</button>
            </div>
        </div>
    </div>
    <CheckoutComponent :modalActive="isModalVisible" @close="isModalVisible = false" :car="selectedCar" />
</div>
</template>

<script>
import CheckoutComponent from './Checkout.vue'
import { carCollection } from '../data/carCollection'

    export default {
        name: 'OrderComponent',
        data() {
            return {
                CarCollection: carCollection,
                isModalVisible: false,
                selectedCar: null
            }
        },
        components: {
            CheckoutComponent
        },
        methods: {
            openModal(car) {
                this.selectedCar = car;
                this.isModalVisible = true;
                this.disableScoll();
            },
            disableScoll() {
                document.body.style.overflow = 'hidden';
            },
        },
    }
</script>

<style scoped>
.order-page {
  max-width: 1200px;
  margin: auto;
}

.car-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(30px, 1fr));
  gap: 40em;
  align-items: start;
  margin-left: -22em;
  padding-top: 40em;
}

.car-item {
    margin-bottom: -50em;
    padding: 10em 0px 5em 0em;
    border-radius: 9px;
    width: 50vh;
    position: relative;
    transition: transform 0.8s ease;
}


.car-img {
    width: 100%;
    height: 22em;
    flex: 1;
    border-radius: 8px;
    object-fit: cover;
    border-radius: 9px;
    border-bottom: 2px solid whitesmoke;
    transition: transform 0.8s ease;
}

.car-item:hover {
    transform: translateY(-1.5em);
    cursor: pointer;
}

.car-item:hover .car-img {
    border: 5px solid rgb(15, 15, 155);
}

h2 {
    position: absolute;
    font-size: 6em;
    font-style: italic;
    padding: 0.5em 1em 1em 1em;
    background-color: rgb(15, 15, 155);
    color: wheat;
    left: 0;
    right: 0;
    margin: 0;
}

h3 {
  margin: 10px 0;
  font-weight: bold;
  font-size: 1.5em;
  color: black
}

h4 {
    margin: 10px 0;
    font-size: 1.1em;
}

button {
    width: 10em;
    font-size: 1.5em;
    margin-top: 0.8em;
    cursor: pointer;
}

button:hover {
    background-color: rgb(15, 15, 155);
    color: wheat;
}

@media (min-width: 3000px) {
    
.car-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(40px, 2fr));
  gap: 60em;
  margin-left: -40em;
}

.car-img {
    width: 100%;
    height: 50em;
}

}

@media only screen and (max-width: 767px) {
    h2 {
        font-size: 3em;
        width: 100%;
        max-width: 100%;
        right: 0;
        left: 0;
        margin: 0 0 0 0;
        padding: 0 2em 0 2em;
    }

    .car-grid {
        display: block;
        margin: 0;
        padding: 5em 0 0 0;
    }

    .car-item {
        margin: 0 0 0 4em;
        padding: 10em 0 0 0;
    }
}

</style>