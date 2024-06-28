<template>
<div class="order-page">
    <h2>Explore our diverse range of premium vehicles</h2>
    <div class="car-grid">
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
            }
        }
    }
</script>

<style scoped>
.order-page {
  max-width: 1200px;
  margin: auto;
  padding-bottom: 20em;
}

.car-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(30px, 1fr));
  gap: 40em;
  align-items: start;
  margin-left: -25em;
  padding-top: 40em;
}

.car-item {
    margin-bottom: -50em;
    padding: 10em 0px 5em 0em;
    /* border: 3px solid black; */
    border-radius: 9px;
    width: 50vh;
    /* background-color: grey; */
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
</style>
