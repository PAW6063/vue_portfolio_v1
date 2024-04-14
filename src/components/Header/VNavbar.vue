<script setup>
    import VNavButton from './VNavButton.vue';
    const navbarItems = [
        { title: 'Home', href: '', current: true },
        { title: 'About', href: '', current: false },
        { title: 'Portfolio', href: '', current: false }
    ]
</script>

<template>
    <nav class="flex flex-row-reverse">
        <VNavButton></VNavButton>
        <ul class="flex">
            <li v-for="item in navbarItems">
                <a>
                    {{ item.title }}
                </a>
            </li>
        </ul>
    </nav>
</template>
