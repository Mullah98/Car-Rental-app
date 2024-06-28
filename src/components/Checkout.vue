<template>
    <div v-show="modalActive" class="modal-overlay">

        <div v-if="modalActive" class="modal-container">
            <img :src="car.image">
            <h3 v-if="car">You have selected the <b>{{ car.year }} {{ car.make }} {{ car.model }}</b></h3>
            <h3>How many days:</h3>
            <h3>Drop off time:</h3><hr>
            <br>
            <h3>Car fee: $4760</h3>
            <h3>Drop off fee: $37</h3>
            <h3>Total: </h3>
            <button>Pay</button>
            <slot />
            <button class="close-btn" @click="closeModal">Close</button>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'CheckoutComponent',
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
            }
        }
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
  padding: 2em; /* Adjusted padding */
  position: relative;
  width: 90%; /* Adjusted width to be more responsive */
  max-width: 800px;
  text-align: left; /* Align text to the left */
  overflow-y: auto; /* Enable scrolling if content overflows */
  border-radius: 10px; /* Optional: Add rounded corners */
}

img {
  max-width: 100%; /* Make sure image is responsive */
  height: auto;
  margin: 1em 10em; /* Add margin for better spacing */
  border: 5px solid black;
}

.close-btn {
  position: absolute;
  top: 10px;
  right: 10px;
  background: transparent;
  border: none;
  font-size: 1em;
  cursor: pointer;
}

h3 {
    margin: 1em 7em;
    font-weight: 200;
    white-space: nowrap;
}

</style>