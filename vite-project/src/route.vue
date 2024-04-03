<script setup>
    import { ref, computed } from 'vue'
    import NotFound from './not-found.vue'
    import PageA from './pagina-a.vue'
    import PageB from './pagina-b.vue'
    import App from './App.vue';
    
    const routes = {
        '/route-a': PageA,
        '/route-b': PageB,
        '/login': App
    }

    const currentPath = ref(window.location.hash)
    window.addEventListener('hashchange', () => {
        currentPath.value = window.location.hash
    })
    const currentView = computed(() =>
    routes[currentPath.value.slice(1)] || NotFound)
</script>

<template>
    <component :is="currentView" />
</template>