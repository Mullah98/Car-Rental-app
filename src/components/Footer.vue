<template>
    <div class="footer-container" v-motion-slide-visible-right>
        <div class="card">
            <h2>Luxury Services</h2>
            <ul>
                <li>Wedding Car Hire</li>
                <li>Photoshoot Car Hire</li>
                <li>Prom Car Hire</li>
                <li>Corporate Car Hire</li>
            </ul>
        </div>

        <div class="card">
            <h2>Follow Us</h2>
            <ul>
                <li>Facebook</li>
                <li>Twitter</li>
                <li>Instragram</li>
                <li>YouTube</li>
            </ul>
        </div>

        <div class="card">
            <h2>Contact Us</h2>
            <ul>
                <li>020 736 786</li>
                <li>Sales@Elitecarrental.co.uk</li>
                <li>699 High Street, Mayfair, London W1J 7JF</li>
            </ul>
        </div>
    </div>

    <button class="home-btn" @click="goHome">Back to home page</button>

    <div class="footer">
        <h4>@Elitecarrental 2024.</h4>
        <p>Designed and developed by Ibrahim Ullah</p>
        <p>Built with Vue 3</p> 
    </div>
</template>

<script>
    export default {
        name: 'FooterComponent',
        methods: {
            goHome() {
                window.location.href = '/'
            }
        }
    }
</script>

<style scoped>
.footer-container {
    display: flex;
    position: relative;
    width: 100%;
    left: 0;
    margin: 0;
    justify-content: center;
}

.card {
    width: 20%;
    height: auto;
    background-color: rgb(114, 105, 105);
    margin-right: 2em;
    color: white;
    border-radius: 5%;
}

h2 {
    font-size: 1.5em;
}

ul {
    display: block;
    text-align: start;
}

li {
    display: block;
    margin: 1em 0em 0em -2em;
    white-space: normal;
    font-size: 1em;
    font-weight: 100;
}

li:hover {
    cursor: pointer;
}

.home-btn {
    position: absolute;
    padding: 1em;
    margin: 8em 5em 0 0;
    right: 0;
    cursor: pointer;
    font-size: 1em;
    font-weight: bold;
    border: none;
    border-radius: 30px;
}

.home-btn:hover {
    background-color: grey;
}

.footer {
    padding: 10em 0 0 0;
}

p {
    font-weight: 200;
    font-style: normal;
    font-size: 1em;
}

@media only screen and (max-width: 767px) {
    .footer-container {
        display: block;
        width: 100%;
    }

    .card {
        width: 100%;
        padding: 4em;
        margin: 2em;
    }

    .home-btn {
        padding: 2em;
        margin: 1em 0em 0 2em;
    }

    .footer {
        margin: 0 auto 2em 6em;
    }
}
</style>