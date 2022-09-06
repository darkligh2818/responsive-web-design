<template>
        <nav class="flex justify-between items-center bg-gray-200 p-4 lg:py-6 lg:px-14 shadow-lg mb-4">
            <div class="flex items-center space-x-2">
                <img class="h-7 lg:h-8" src="../assets/logo.png" alt="Alt">
                <h1 class="text-xl text-pink-700 font-serif font-bold lg:text-2xl">{{ brand }}</h1>
            </div>
            <div>
                <ul class="flex space-x-3 lg:space-x-10 lg:ml-6">
                    <router-link v-for="yollanma in yollanmalar" :key="yollanma" :to="yollanma.manzil" class=" text-pink-700 text-md uppercase font-semibold font-sans lg:font-bold lg:tracking-wider lg:text-[19px]">{{ yollanma.nom }}</router-link>
                </ul>
            </div>
            <div class="hidden lg:flex items-center space-x-3">
                <input v-model="title" class="py-1 rounded-lg tracking-widest font-semibold font-sans border outline-none border-amber-400 pl-2" type="text" placeholder="Enter Your Name">
                <button @click="changeBrand()" class="fa-sharp fa-solid fa-magnifying-glass text-xl text-amber-700"></button>
            </div>
        </nav>
    <router-view></router-view>
</template>

<script>
export default {
    name: 'NavBar',
    data() {
        return {
            yollanmalar: [
                {
                    manzil: '/',
                    nom: 'Home',
                },
                {
                    manzil: '/about',
                    nom: 'About'
                },                
            ],            
            title: '',
            brand: 'Portfolio',
        }
    },
    methods: {
        changeBrand() {
            if(this.brand == "") {
                alert('Yozish esingdami botalogim');
            } else {
                this.brand = this.title;
            }
        }
    }
}
</script>