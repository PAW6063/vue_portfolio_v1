<script setup>
    
    const navbarItems = [
        { title: 'Home', href: '', current: true },
        { title: 'About', href: '', current: false },
        { title: 'Portfolio', href: '', current: false }
    ]

    const menu = {
        open: false,
        position: 'top-[10dvh]',
        d: [
            "M3.75 5.25h16.5m-16.5 4.5h16.5m-16.5 4.5h16.5m-16.5 4.5h16.5",
            "M6 18 18 6M6 6l12 12"
        ]
    }

    function MenuButton(e) {
        const svg = document.getElementById('menuSVG');
        const menuList = document.getElementById('NavMenu');
        if(menu.open){
            svg.setAttribute('d', menu.d[0]);
            menuList.classList.add("top-[-30dvh]");
            menuList.classList.remove("top-[10dvh]");
        } else {
            svg.setAttribute('d', menu.d[1]);
            menuList.classList.add("top-[10dvh]");
            menuList.classList.remove("top-[-30dvh]");
        }
        
        menu.open = !menu.open;
    }
</script>

<template>
    <nav class=" bg-red-200 w-1/2 flex flex-row-reverse">
        <button @click="MenuButton" class="bg-white border h-full w-auto md:hidden">
            <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5"
                stroke="currentColor" class="h-2/3 m-auto">
                <path stroke-linecap="round" stroke-linejoin="round"
                    d="M3.75 5.25h16.5m-16.5 4.5h16.5m-16.5 4.5h16.5m-16.5 4.5h16.5" id="menuSVG"/>
            </svg>
        </button>
        <ul id="NavMenu"
            class="bg-red-500 absolute w-screen h-[30svh] flex flex-col justify-around top-[-30dvh] z-[-1] md:static md:flex md:flex-row md:z-auto md:h-full"
        >
            <li v-for="item in navbarItems" class="mx-auto grow flex items-center justify-center">
                <a>
                    {{ item.title }}
                </a>
            </li>
        </ul>
    </nav>
</template>
