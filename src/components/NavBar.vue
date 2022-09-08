<template>
        <nav class="flex justify-between items-center bg-gray-200 p-4 lg:py-6 lg:px-14 shadow-lg mb-4 relative">
            <div class="flex items-center space-x-2">
                <img class="h-7 lg:h-8" src="../assets/logo.png" alt="Alt">
                <h1 class="text-xl text-pink-700 font-serif font-bold lg:text-2xl">{{ $store.state.brand }}</h1>
            </div>
            <!-- mobile menu -->
            <div class="lg:hidden">
                <button @click="openMenu()" class="fa-solid fa-bars absolute right-6 top-2 text-pink-700 font-semibold text-xl active:bg-gray-300 rounded-lg px-1 py-2">
                </button>
                <div v-if="result" class="relative">
                    <ul class="lg:flex lg:space-x-10 lg:ml-6 absolute flex flex-col top-2 px-4 py-3 right-7 w-90 h-90 bg-gray-300 shadow-lg rounded-lg">
                        <router-link v-for="yollanma in yollanmalar" :key="yollanma" :to="yollanma.manzil" class=" text-pink-700 text-md uppercase font-bold font-sans lg:font-bold lg:tracking-wider lg:text-[19px]">{{ yollanma.nom }}</router-link>
                    </ul>
                </div>
            </div>
            <!-- /mobile menu -->

            <!-- desktop menu -->
            <div class="hidden lg:inline-block">
                <ul class="lg:flex lg:space-x-10 lg:ml-6">
                    <router-link v-for="yollanma in yollanmalar" :key="yollanma" :to="yollanma.manzil" class=" text-pink-700 text-md uppercase font-semibold font-sans lg:font-bold lg:tracking-wider lg:text-[19px]">{{ yollanma.nom }}</router-link>
                </ul>
            </div>
            <!-- /desktop menu -->
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
            result: false,
        }
    },
    methods: {
        changeBrand() {
            if(this.store.state.brand == "") {
                alert('Enter Your brand');
            } else {
                this.$store.state.brand = this.title;
            }
        },
        openMenu() {
            this.result = !this.result;
        }
    }
}
</script>