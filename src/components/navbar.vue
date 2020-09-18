<template>
    <div id="navbar">
        <h1 class="center">KOTCHAKORN M.</h1>
        <h3 class="center">- {{$route.name}} -</h3>
        <hr>
        <div class="menu center">
            <div class="menuLink">
                <router-link to="/">
                    <img src="../assets/icons/portfolio.png" />
                </router-link>
                <h6>Portfolio</h6>
            </div>
            <div class="menuLink">
                <router-link to="/About">
                    <img src="../assets/icons/profile.png" />
                </router-link>
                <h6>About</h6>
            </div>
            <div class="menuLink">
                <router-link to="/contact">
                    <img src="../assets/icons/contact.png" />
                </router-link>
                <h6>Contact</h6>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'navbar',
    data(){
        return{
            windowWidth: window.innerWidth
        }
    },
    mounted() {
        window.addEventListener("resize", () => {
        this.windowWidth = window.innerWidth;
        });
    },
}
</script>
<!-- v-if="this.windowWidth > 767" -->