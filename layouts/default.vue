<template>
    <div class="container mx-auto max-w-4xl">
        <header class="flex justify-between items-start md:items-center mt-5">
          <div class="flex items-center md:space-x-10">
            <div class="hidden md:block">
              <NuxtLink to="/" class="text-xl font-semibold p-2 hover:bg-gray-200 dark:hover:bg-gray-800">Vidhuprasad</NuxtLink>
            </div>
            <Menu />
          </div>
          <colorMode />
        </header>
        <main class="p-2 mt-10">
          <slot />
        </main>
    </div>
</template>

<script setup>


useHead({
  titleTemplate : '%s - Vidhuprasad',
  link: [
    {
      rel: 'preconnect',
      href: 'https://fonts.googleapis.com'
    },
    {
      rel: 'stylesheet',
      href: 'https://fonts.googleapis.com/css2?family=Roboto&display=swap',
      crossorigin: ''
    }
  ]
})

</script>

<style>
body{
  font-family: 'Roboto';
}

</style>