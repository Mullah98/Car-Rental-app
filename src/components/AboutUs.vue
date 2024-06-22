<template>
    <div class="about-page">
        <div class="card">
            <div class="card-item"><button @click="toggleCard(1)">What do we do?</button><p :class="{ 'show-card' : isOpen === 1}">information</p></div>
            <div class="card-item"><button>Our policy</button></div>
            <div class="card-item"><button>Something else here</button></div>

        </div>
    </div>
</template>

<script>
    export default {
        name: 'AboutUsComponent',
        data() {
            return {
                isOpen: false,
            }
        },
        methods: {
            toggleCard(cardNum) {
                this.isOpen = (this.isOpen === cardNum) ? false : cardNum;
            }
        }
    }
</script>

<style scoped>
.about-page {
    margin-top: 50em;
}

.card {
    border: 5px solid blue;
    display: block;
}


button {
    font-size: 3em;
    background-color: rgb(2, 2, 51);
    color: wheat;
    width: 100%;
    cursor: pointer;
}

.card p {
    display: none;
}

.show-card {
    display: block;
    padding: 20px;
}
</style>