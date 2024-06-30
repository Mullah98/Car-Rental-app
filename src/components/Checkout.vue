<template>
    <div v-show="modalActive" class="modal-overlay">

        <div v-if="modalActive" class="modal-container">
            <img :src="car.image">
            <h3 v-if="car">You have selected the <b>{{ car.year }} {{ car.make }} {{ car.model }}</b></h3>
            <h3>How many days: <button @click="increaseDays">+</button> {{ daysLength }} <button @click="decreaseDays">-</button></h3>
            <h3>Drop off time: 
                <button class="time-btn" :class="{ 'highlighted' : isTimeSelected === 1}" @click="selectTime(1)">8:00am</button>
                <button class="time-btn" :class="{ 'highlighted' : isTimeSelected === 2}" @click="selectTime(2)">10:00am</button>
                <button class="time-btn" :class="{ 'highlighted' : isTimeSelected === 3}" @click="selectTime(3)">12:00pm</button>
                <button class="time-btn" :class="{ 'highlighted' : isTimeSelected === 4}" @click="selectTime(4)">2:00pm</button>
            </h3>
            <label for="date"><h3>Choose a date:</h3></label>
            <VueDatePicker v-model="selectedDate" format="dd-MM-yyyy"/>
            <hr><br>
            <h3>Car fee: <b>£{{ car.price }}</b></h3>
            <h3>Drop off fee: <b>£{{ dropOffFee }}</b></h3>
            <h3>Total: <b>£{{ totalAmount }}</b></h3>
            <button class="pay-btn">Confim order</button>
            <slot />
            <button class="close-btn" @click="closeModal">Close</button>
        </div>
    </div>
</template>

<script>
import VueDatePicker from '@vuepic/vue-datepicker';
import '@vuepic/vue-datepicker/dist/main.css';

    export default {
        name: 'CheckoutComponent',
        data() {
            return {
                dropOffFee: 40,
                daysLength: 1,
                maxDays: 7,
                minDays: 1,
                selectedDate: null,
                isTimeSelected: 0,
            }
        },
        components: {
            VueDatePicker
        },
        props: {
            modalActive: {
                type: Boolean,
                default: false
            },
            car: {
                type: Object,
                default: null
            },
        },
        methods: {
            closeModal() {
                this.$emit('close')
            },
            selectTime(buttonNum) {
                this.isTimeSelected = buttonNum;
            },
            increaseDays() {
                if (this.daysLength < this.maxDays) {
                this.daysLength++;
                } else {
                    alert('You can only hire a vehicle for a maximum of 7 days')
                }
            },
            decreaseDays() {
                if (this.daysLength > this.minDays) {
                this.daysLength--;
                }
            },
        },
        computed: {
            totalAmount() {
                return (this.car ? this.car.price : 0) * this.daysLength + this.dropOffFee;
            }
        },
        watch: {
            car(newCar, oldCar) {
                if (newCar !== oldCar) {
                    this.daysLength = 1;
                }
            }
        },
    }
</script>

<style scoped>
.modal-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.9);
  display: flex;
  justify-content: center;
  align-items: center;
}

.modal-container {
  background-color: rgb(201, 200, 200);
  padding: 2em;
  position: relative;
  width: 90%;
  max-width: 800px;
  text-align: left;
  overflow-y: auto;
  border-radius: 10px;
}

img {
  max-width: 100%;
  height: auto;
  margin: 1em 10em;
  border: 5px solid black;
}

.close-btn {
  position: absolute;
  top: 10px;
  right: 10px;
  background: transparent;
  border: none;
  font-size: 1.2em;
}

h3 {
    margin: 1em 7em;
    font-weight: 200;
    white-space: nowrap;
}

.time-btn {
    margin-right: 1em;
    font-size: 0.9em;
}

.highlighted {
    border: 3px solid blue;
}

.dp__main {
    padding: 0 0 1em 0;
    width: 50%;
    left: 15%;
}

.pay-btn {
    margin: 1em 0 2em 20em;
    padding: 1em;
    font-size: 1em;
}

button {
    cursor: pointer;
}
</style>