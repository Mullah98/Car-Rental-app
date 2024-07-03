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
                    {name: 'Rent car', path: 'main'},
                    {name: 'About Us', path: 'aboutUs'},
                    {name: 'Contact', path: 'contact'},
                ]
            }
        }
    }
</script>

<style>

li {
    display: inline;
    width: 100%;
    font-size: 1.5em;
    padding: 2em;
    margin: 2em;
    font-weight: bolder;
}

a {
    text-decoration: none;
    color: rgb(15, 15, 155);
}

a:hover {
    color: wheat;
}
</style>