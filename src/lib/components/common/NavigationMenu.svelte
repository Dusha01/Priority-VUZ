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

  onMount(() => {
      checkMobile();
      
      const menu = document.querySelector('.menu_priority') as HTMLElement; 
      if (menu) {
          menuHeight = menu.offsetHeight;
      }

      if (menuHeight === 0) {
          setTimeout(() => {
              const menu = document.querySelector('.menu_priority') as HTMLElement; 
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
  class="menu_priority w-full bg-white shadow-lg z-40 transition-all duration-300 overflow-hidden"
  class:fixed={sticky}
  class:top-0={sticky}
  class:left-0={sticky}
  class:relative={!sticky}>
  <div class="container mx-auto">
      <div class="lg:hidden flex justify-between items-center p-4">
          <div class="text-lg font-semibold">Меню</div>
          <button class="p-2 rounded-md focus:outline-none" on:click={toggleMobileMenu} aria-label="Меню">
              <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                  {#if isMobileMenuOpen}
                      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
                  {:else}
                      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
                  {/if}
              </svg>
          </button>
      </div>

      <div
          class="hidden lg:flex justify-center space-x-2 p-2"
          class:flex-col={isMobileMenuOpen}
          class:space-y-2={isMobileMenuOpen}
          class:space-x-0={isMobileMenuOpen}
          class:p-4={isMobileMenuOpen}
          class:block={isMobileMenuOpen}>
          <a href="#about" class="block px-4 py-2 rounded-full hover:bg-gray-100 transition whitespace-nowrap" on:click={closeMobileMenu}>
              <span>О ПРОГРАММЕ</span>
          </a>
          <a href="#mission" class="block px-4 py-2 rounded-full hover:bg-gray-100 transition whitespace-nowrap" on:click={closeMobileMenu}>
              <span>МИССИЯ</span>
          </a>
          <a href="#team" class="block px-4 py-2 rounded-full hover:bg-gray-100 transition whitespace-nowrap" on:click={closeMobileMenu}>
              <span>КОМАНДА</span>
          </a>
          <a href="#StrategicProject" class="block px-4 py-2 rounded-full hover:bg-gray-100 transition whitespace-nowrap" on:click={closeMobileMenu}>
              <span>СТРАТЕГИЧЕСКИЙ ПРОЕКТ</span>
          </a>
          <a href="#documents-section" class="block px-4 py-2 rounded-full hover:bg-gray-100 transition whitespace-nowrap" on:click={closeMobileMenu}>
              <span>ПРОГРАММА РАЗВИТИЯ</span>
          </a>
      </div>
  </div>
</nav>