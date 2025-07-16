<script lang="ts">
    import { onMount } from 'svelte';

    let sticky = false;
    let menuHeight = 0;
    let isMobileMenuOpen = false;
    let isMobile = false;

    function toggleMobileMenu() {
        isMobileMenuOpen = !isMobileMenuOpen;
    }

    function closeMobileMenu() {
        isMobileMenuOpen = false;
    }

    function goBack() {
        window.history.back();
    }

    onMount(() => {
        checkMobile();

        const menu = document.querySelector('.menu_custom') as HTMLElement;
        if (menu) {
            menuHeight = menu.offsetHeight;
        }

        if (menuHeight === 0) {
            setTimeout(() => {
                const menu = document.querySelector('.menu_custom') as HTMLElement;
                if (menu) {
                    menuHeight = menu.offsetHeight;
                }
            }, 0);
        }

        window.addEventListener('scroll', handleScroll);
        window.addEventListener('resize', handleResize);

        return () => {
            window.removeEventListener('scroll', handleScroll);
            window.removeEventListener('resize', handleResize);
        };
    });

    function checkMobile() {
        isMobile = window.innerWidth < 1024;
    }

    function handleResize() {
        checkMobile();
        if (!isMobile) {
            isMobileMenuOpen = false;
        }
    }

    function handleScroll() {
        const pageTop = document.querySelector('.page-top') as HTMLElement;
        if (!pageTop) return;

        const pageTopRect = pageTop.getBoundingClientRect();
        const pageTopBottom = pageTopRect.bottom + window.scrollY;

        sticky = window.scrollY > pageTopBottom - menuHeight;
    }
</script>

<nav
        class="menu_custom w-full bg-white shadow-lg z-40 transition-all duration-300 overflow-hidden mt-10"
        class:fixed={sticky}
        class:top-0={sticky}
        class:left-0={sticky}
        class:relative={!sticky}>
    <div class="container mx-auto">
        <div class="lg:hidden flex justify-between items-center p-4">
            <button
                    on:click={goBack}
                    class="flex items-center p-2 rounded-md hover:bg-gray-100 transition"
                    aria-label="Назад">
                <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" viewBox="0 0 24 24" stroke="currentColor">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 19l-7-7m0 0l7-7m-7 7h18" />
                </svg>
            </button>
            <div class="text-lg font-semibold">Меню</div>
            <button class="p-2 rounded-md focus:outline-none" on:click={toggleMobileMenu} aria-label="Меню">
                <svg class="w-6 h-6" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                    {#if isMobileMenuOpen}
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
                    {:else}
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
                    {/if}
                </svg>
            </button>
        </div>

        <div class="hidden lg:flex items-center p-2">
            <button
                    on:click={goBack}
                    class="flex items-center px-4 py-2 rounded-full hover:bg-gray-100 transition whitespace-nowrap mr-auto"
                    aria-label="Назад">
                <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 mr-1" viewBox="0 0 24 24" stroke="currentColor">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 19l-7-7m0 0l7-7m-7 7h18" />
                </svg>
                <span>Назад</span>
            </button>

            <div class="flex absolute left-1/2 transform -translate-x-1/2 space-x-2">
                <a href="#documents" class="block px-4 py-2 rounded-full hover:bg-gray-100 transition whitespace-nowrap" on:click={closeMobileMenu}>
                    <span>О НАС</span>
                </a>
                <a href="#contacts" class="block px-4 py-2 rounded-full hover:bg-gray-100 transition whitespace-nowrap" on:click={closeMobileMenu}>
                    <span>КОНТАКТЫ</span>
                </a>
            </div>
        </div>

        {#if isMobileMenuOpen}
            <div class="lg:hidden flex flex-col p-4 space-y-2">
                <a href="#documents" class="block px-4 py-2 rounded-full hover:bg-gray-100 transition" on:click={closeMobileMenu}>
                    <span>О НАС</span>
                </a>
                <a href="#contacts" class="block px-4 py-2 rounded-full hover:bg-gray-100 transition" on:click={closeMobileMenu}>
                    <span>КОНТАКТЫ</span>
                </a>
            </div>
        {/if}
    </div>
</nav>