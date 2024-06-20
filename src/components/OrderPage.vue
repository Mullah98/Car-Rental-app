<template>
    <div v-for="car in CarCollection" :key="car">
        Order some whippsss
        <h1>We are going to buy some stuff</h1>
        <!-- <img :src="car.image" alt="bmw"> -->
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
                    {car: 'BMW', image: bmw},
                    {car: 'Aston Martin', image: astonMartin},
                    {car: 'Audi', image: audi},
                    {car: 'Bentley', image: bentley},
                    {car: 'Bugatti', image: bugatti},
                    {car: 'Ferarri', image: ferrari},
                    {car: 'Ford', image: ford},
                    {car: 'Lamborghini', image: lamborghini},
                    {car: 'Land Rover', image: landRover},
                    {car: 'McLaren', image: mclaren},
                    {car: 'Mercedes', image: mercedes},
                    {car: 'Porsche', image: porsche}
                ]
            }
        }
    }
</script>

<style>

</style>