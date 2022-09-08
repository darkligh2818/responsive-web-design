<template>
    <section class="mt-8 lg:mt-16">
      <div>
        <h1 class="py-5 px-2 text-3xl font-semibold text-slate-800 font-sans text-center lg:text-6xl lg:px-[250px]">Rapidly build modern websites without ever leaving your HTML...</h1>
        <p class="px-4 py-1 text-center text-sans text-lg font-medium text-slate-600 lg:px-[350px] lg:text-2xl">
          A utility-first CSS framework packed with classes like 
          <span class="text-pink-700">flex</span>, 
          <span class="text-pink-700">pt-4</span>, 
          <span class="text-pink-700">text-center</span> and 
          <span class="text-pink-700">rotate-90</span> that can be composed to build any design, directly in your markup.
        </p>
        <div class="px-6 mt-4 lg:mt-10 lg:px-[350px] lg:space-x-6 lg:flex">
          <router-link to="/about" class="inline-block text-center w-full py-2 rounded-lg text-white bg-slate-800 hover:bg-slate-600 lg:py-4 lg:text-lg lg:w-1/4 lg:rounded-xl">Get Started</router-link>
          <div class="lg:w-3/4 relative hidden lg:flex items-center">
            <input type="text" class="pl-10 w-full border-2 outline-none border-slate-600 rounded-xl focus:border-blue-700 text-lg font-semibold tracking-wider lg:py-4" placeholder="Quick search...">
            <svg class="w-6 h-6 absolute left-2 text-slate-700 font-bold text-xl" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" d="M21 21l-5.197-5.197m0 0A7.5 7.5 0 105.196 5.196a7.5 7.5 0 0010.607 10.607z" />
            </svg>
          </div>
        </div>
      </div>
    </section>
</template>

<script>


export default {
  name: 'HomeView',
}
</script>
