<template>
<div class="car-container">
    <h2>Explore our diverse range of premium vehicles</h2>
    <div class="car-grid">
    <div v-for="(car, i) in CarCollection" :key="i">
        <div class="car-item">
        <img :src="car.image" alt="Car Image" class="car-img">
        <h3>{{ car.make }}</h3><hr>
        <h4>Model: {{ car.model }}</h4><hr>
        <h4>Engine: {{ car.engine }}</h4><hr>
        <h4>Speed: {{ car.power }}</h4><hr>
        <h4>Year: {{ car.year }}</h4><hr>
    </div>
    </div>
    </div>
</div>
</template>

<script>
import astonMartin from '../assets/aston-martin-v12-speedster-dbr1.jpg'
import audi from '../assets/audi-r8-v10-decennium-2019.jpg'
import bentley from '../assets/bentley-bentayga-s-black-edition-2024.jpg'
import bmw from '../assets/bmw-m5-f90-cs-2022.jpg'
import bugatti from '../assets/bugatti-chiron-sport-les-legendes-du-ciel-2021.jpg'
import ferrari from '../assets/ferrari-812-competizione-2021.jpg'
import ford from '../assets/ford-mustang-shelby-gt500-2022.jpg'
import lamborghini from '../assets/lamborghini-urus-s-2023.jpg'
import landRover from '../assets/land-rover-defender-110-v8-2022.jpg'
import mclaren from '../assets/mclaren-765lt-spider-2022.jpg'
import mercedes from '../assets/mercedes-amg-gt3-race.jpg'
import porsche from '../assets/porsche-911-992-gt3-rs-2023.jpg'

    export default {
        name: 'OrderComponent',
        data() {
            return {
                CarCollection: [
                    {make: 'Aston Martin', model:'V12 Speedster DBR1', engine:'5.2L V12 Twin-Turbo', power:700, year:2023, image: astonMartin},
                    {make: 'Audi', model:'R8 V10 Decennium', engine:'5.2L V10', power:620, year:2023, image: audi},
                    {make: 'Bentley', model:'Bentayga S Black-edition', engine:'4.0L V8 Twin-Turbo', power:542, year: 2023, image: bentley},
                    {make: 'BMW', model:'F90 M5 Competition', engine:'4.4L V8 Twin-Turbo', power:617, year:2023, image: bmw},
                    {make: 'Bugatti', model:'Chiron Sport', engine:'8.0L W16 Quad-Turbo', power:1479, year:2023, image: bugatti},
                    {make: 'Ferarri', model:'812 Competizione', engine:'6.5L V12', power:830, year: 2023, image: ferrari},
                    {make: 'Ford', model:'Mustang Shelby Gt500', engine:'5.2L Supercharged V8', power:760, year:2023, image: ford},
                    {make: 'Lamborghini', model:'Urus S', engine:'4.0L V8', power:657, year: 2023, image: lamborghini},
                    {make: 'Land Rover', model:'Defender 110 v8', engine:'5.0L Supercharged V8', power:518, year: 2023, image: landRover},
                    {make: 'McLaren', model:'765lt Spider', engine:'4.0L Twin-Turbo V8', power:765, year: 2023, image: mclaren},
                    {make: 'Mercedes Benz', model:'AMG Gt3-race', engine:'6.3L V8', power:580, year: 2023, image: mercedes},
                    {make: 'Porsche', model:'911 Gt3 RS', engine:'4.0L Flat-6', power:520, year: 2023, image: porsche}
                ]
            }
        }
    }
</script>

<style scoped>
.car-container {
  max-width: 1200px;
  margin: auto;
  padding-bottom: 20em;
}

.car-grid {
  display: grid;
  grid-template-columns: 60px 60px 60px;
  gap: 40em;
  align-items: start;
  margin-left: -19em;
  padding-top: 40em;
}

.car-item {
    margin-bottom: -20em;
    padding: 10em 0px 0px 0px;
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
    color: white;
    left: 0;
    right: 0;
    margin: 0;
}

h3, h4 {
  margin: 10px 0;
}
</style>
