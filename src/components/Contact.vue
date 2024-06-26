<template>
    <div class="contact">
        <form>
            <h2>Contact us!</h2>
            <p>Our team is happy to answer any questions you have. Fill out the form below and we'll be in contact as soon as possible.</p>
            <label>Name: <input type="text" placeholder="Enter your name here" v-model="name" @input="validateName"></label>
            <label>Email: <input type="text" placeholder="Sales@Elitecarhire.com"></label>
            <label>Number: <input type="text" placeholder="Enter number" v-model="number" @input="validateNumber"></label>
            <button @input="handleSubmit">Submit</button>
        </form>
        <p v-if="errorText" class="error">{{ errorText }}</p>
    </div>
</template>

<script>
    export default {
        name: 'ContactComponent',
        data() {
            return {
                name: '',
                email: '',
                number: '',
                errorText: ''
            }
        },
        methods: {
            validateName(event) {
                const text = event.target.value;
                if (/[^a-zA-Z\s]/.test(text)) {
                this.name = text.replace(/[^a-zA-Z\s]/g, '');
                this.errorText = 'No numbers or special characters allowed'
                } else {
                this.errorText = '';
                this.name = text;
                }
            },
            validateNumber(event) {
                const digits = event.target.value;
                if (/^\d{0,11}$/.test(digits)) {
                    this.number = digits;
                    this.errorText = '';
                } else {
                    this.errorText = 'Enter valid number';
                }
            },
            handleSubmit() {
                if (this.name !== '' && this.email !== '' && this.number !== '') {
                    this.errorText = 'Success!'
                }
            }
        }
    }
</script>

<style scoped>
.contact {
    margin: 25em 0 10em 0;
}
h2 {
    font-size: 5em;
    background-color: rgb(15, 15, 155);
    color: wheat;
}
p {
    font-size: 2em;
    margin: 1em 0 2em 0;
    color: rgb(15, 15, 155);
}

.error {
    font-size: 1em;
    color: red;
}

label {
    font-size: 1.2em;
}
input {
    font-size: 1em;
    margin-right: 2em;
}
button {
    font-size: 1.2em;
}
</style>