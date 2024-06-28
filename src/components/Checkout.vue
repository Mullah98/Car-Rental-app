<template>
    <div v-show="modalActive" class="modal-overlay">

        <div v-if="modalActive" class="modal-content">
            <h3 v-if="car">You have selected the {{ car.year }} {{ car.make }} {{ car.model }}</h3>
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
.modal-content {
    background-color: rgb(201, 200, 200);
    padding: 20em;
    position: relative;
}

.close-btn {
  position: absolute;
  top: 10px;
  right: 10px;
  background: transparent;
  border: none;
  font-size: 1em;
}

</style>