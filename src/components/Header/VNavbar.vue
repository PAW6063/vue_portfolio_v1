<script setup>
    const navbarItems = [
        {title: 'Home', href: '', current: true },
        {title: 'About', href: '', current: false },
        {title: 'Portfolio', href: '', current: false }
    ]
</script>

<template>
    <nav>
        <button>
            <span>
                
            </span>
        </button>
        <ul>
            <li v-for="item in navbarItems" >
                <a>
                    {{ item.title }}
                </a>
            </li>
        </ul>
    </nav>
</template>
