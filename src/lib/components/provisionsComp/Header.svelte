<script lang="ts">
    import DVGUPSLogo from '../../assets/logo/dvgups.png';
    import prioritetLogo from '../../assets/logo/priority.png';
    import socialCenterLogo from '../../assets/logo/socioСenter.png';
    import { onMount } from 'svelte';
  
    let headerHeight = 0;
    let isHeaderVisible = true;
  
    onMount(() => {
      const header = document.querySelector('header');
      if (header) {
        headerHeight = header.offsetHeight;
      }
  
      if (headerHeight === 0) {
        setTimeout(() => {
          const header = document.querySelector('header');
          if (header) {
            headerHeight = (header.offsetHeight) + 400;
          }
        }, 0);
      }
  
      window.addEventListener('scroll', handleScroll);
  
      return () => {
        window.removeEventListener('scroll', handleScroll);
      };
    });
  
    function handleScroll() {
      if (headerHeight === 0) return; 
  
      isHeaderVisible = window.scrollY <= headerHeight * 2;
    }
  
    $: headerClasses = `fixed top-0 left-0 w-full z-50 bg-white shadow-md py-2 transition-transform duration-300 ${
      isHeaderVisible ? '' : 'translate-y-[-200%]'
    }`;
</script>
  
<header class={headerClasses}>
    <div class="container mx-auto px-4">
        <div class="flex justify-between items-center">
            <div class="flex items-center space-x-4 gap-x-8">
                <a href="https://sociocenter.info" target="_blank" rel="noopener noreferrer">
                    <img src={socialCenterLogo} alt="Социо Центр" class="h-18" />
                </a>
                <a href="https://priority2030.ru" target="_blank" rel="noopener noreferrer">
                    <img src={prioritetLogo} alt="Приоритет 2030" class="h-18" />
                </a>
                <a href="https://dvgups.ru/" target="_blank" rel="noopener noreferrer">
                    <img src={DVGUPSLogo} alt="ДВГУПС" class="h-18" />
                </a>
            </div>
        </div>
    </div>
</header>  