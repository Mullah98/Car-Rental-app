<template>
    <div class="footer">
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
</template>

<script>
    export default {
        name: 'FooterComponent'
    }
</script>

<style scoped>
.footer {
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
</style>