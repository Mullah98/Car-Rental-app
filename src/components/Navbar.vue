<template>
    <div class="navbar">
        <li v-for="item in navItems" :key="item">
            <a :href="`#${item.path}`">{{ item.name }}</a>
        </li>
    </div>
</template>

<script>
    export default {
        name: 'NavbarComponent',
        data() {
            return {
                navItems: [
                    {name: 'Home', path: '/'},
                    {name: 'Rent car', path: 'main'},
                    {name: 'About Us'},
                    {name: 'Contact'}
                ]
            }
        }
    }
</script>

<style>

li {
    display: inline;
    width: 100%;
    border: 4px solid blue;
    font-size: 1.5em;
    padding: 2em;
    margin: 2em;
    font-weight: bolder;
}

</style>