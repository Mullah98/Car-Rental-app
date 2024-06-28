<template>
    <div class="checkout">
        <div class="payment-tab">
            Payment here
            <button>Close</button>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'CheckoutComponent',
    }
</script>

<style scoped>
.payment-tab {
    background-color: aqua;
    position: relative;
    padding: 5em 10em 10em 5em ;
}
</style>