<template>
    <div class="about-page" v-motion-slide-visible-bottom>
        <div class="card">
            <div class="card-item">
                <button @click="toggleCard(1)">Who are we?</button>
                <p v-bind:class="isOpen === 1 ? 'show-card' : ''" v-motion-slide-visible-top>
                    Founded in 2010, we are a premier car rental company based in the luxurious heart of London, rapidly expanding our presence in the market of luxury vehicles.
                     Our clientele includes prominent individuals such as Tom Cruise and George Clooney, who trust us for our exclusive travel needs.
                    Join us to embark our prestigious fleet and exceptional service, tailored to provide unmatched luxury and convenience in every rental experience.
                </p>
            </div>
            <div class="card-item">
                <button @click="toggleCard(2)">Why choose us?</button>
                <p v-bind:class="isOpen === 2 ? 'show-card' : ''" v-motion-slide-visible-top>
                    We stand out with one of the most exclusive fleets, featuring some of the newest and rarest cars available. Whether you desire the latest models or seek the thrill of driving a limited edition, our collection promises to exceed expectations.
                    We prioritize convenience with flexible arrangements. With just a 24-hour notice, we offer seamless drop-off and pick-up services, ensuring your luxury rental experience fits seamlessly into your schedule.
                </p>
            </div>
            <div class="card-item">
                <button @click="toggleCard(3)">What do our customers say?</button>
                <div v-bind:class="isOpen === 3 ? 'thirdCard' : 'hidden'" v-motion-slide-visible-top>
                    <div class="thirdItem"><h3>Brilliant, quick service. Cars were awesome!</h3><h4>Alex, Birmingham<br>⭐ 4.7</h4></div>
                    <div class="thirdItem"><h3>Couldn't ask for a better group to work with</h3><h4>Sophie, Liverpool<br>⭐ 4.6</h4></div>
                    <div class="thirdItem"><h3>Happy with the service. Will be back soon!</h3><h4>Jordan, Leeds<br>⭐ 4.9</h4></div>
                    <div class="thirdItem"><h3>Exceptional experience from start to finish</h3><h4>Chris, Sheffield<br>⭐ 4.8</h4></div>
                    <div class="thirdItem"><h3>Top-notch service and great cars! Thanks lads</h3><h4>Pat, Bristol<br>⭐ 4.7</h4></div>
                    <div class="thirdItem"><h3>Highly recommend, fantastic team!</h3><h4>Jamie, Newcastle<br>⭐ 4.9</h4></div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'AboutUsComponent',
        data() {
            return {
                isOpen: 0,
            }
        },
        methods: {
            toggleCard(cardNum) {
                this.isOpen = (this.isOpen === cardNum ? 0 : cardNum);
                console.log('You clicked on card 1', this.isOpen);
            }
        },
    }
</script>

<style scoped>
.about-page {
    margin-top: 50em;
    padding-bottom: 2em;
}

.card {
    display: block;
}


button {
    font-size: 3em;
    background-color: rgb(15, 15, 155);
    color: wheat;
    width: 100%;
    cursor: pointer;
    border: 1px solid wheat;
}

.card p {
    display: none;
    font-size: 2em;
}

.show-card {
    display: block !important;
    padding: 2em;
}

.hidden {
    display: none;
}

.thirdItem {
    width: 6.5em;
    height: auto;
    display: inline-block;
    font-size: 4em;
    text-align: start;
    padding: 0 1em 0 3em;
    margin: 3px 3px 0 0;
    background-color: rgb(174, 168, 168);
    border-radius: 3%;

    h3 {
        margin-right: 1.5em;

        font-size: 0.8em;
    }

    h4 {
        margin-right: 1.5em;
        font-size: 0.4em;
        font-style: italic;
    }
}

</style>