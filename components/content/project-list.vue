<template>
    <div class="not-prose">
        <div>Projects</div>
        <section v-if="pending">Loading...</section>
        <section v-else-if="error">Something went wrong...Try again!</section>
        <section v-else>
            <ul class="grid grid-cols-1 gap-4">
                <li v-for="repository in repos" :key="repository.id"
                class="border border-gray-200 dark:border-gray-700 rounded-sm p-4 hover:bg-gray-200 dark:hover:bg-gray-700 font-mono">
                    <a :href="repository.html_url" target="_blank">
                        <div class="flex items-center justify-between text-sm">
                            <div class="font-semibold">{{ repository.name }}</div>
                            <div>{{ repository.stargazers_count }} *</div>
                        </div>
                        <p class="text-sm">
                            {{ repository.description }}
                        </p>
                    </a>
                </li>
            </ul>
        </section>
    </div>
</template>

<script setup>
const {error, pending, data} = await useFetch('https://api.github.com/users/piotr-jura-udemy/repos')

const repos = computed(() => data.value.filter(repo => repo.description))
</script>