<script lang="ts">
    import prioritetLogo from '../assets/logo/priority.png';
    import ministryLogo from '../assets/logo/ministry.png';
    import { onMount } from 'svelte';
  
    let isVisible = false;
    let sectionRef: HTMLElement;
  
    onMount(() => {
      const observer = new IntersectionObserver(
        (entries) => {
          entries.forEach((entry) => {
            isVisible = entry.isIntersecting;
          });
        },
        { threshold: 0.1 }
      );
  
      if (sectionRef) {
        observer.observe(sectionRef);
      }
      
      return () => {
        if (sectionRef) {
          observer.unobserve(sectionRef);
        }
      };
    });
</script>
  
<section
    id="about"
    class="py-12 md:py-24 bg-gradient-to-br from-gray-50 to-gray-100"
    bind:this={sectionRef}
>
    <div class="container mx-auto px-4 sm:px-6 h-full">
        <div class="flex flex-col lg:flex-row gap-6 lg:gap-16 items-stretch h-full">
            <div class="hidden lg:flex lg:w-24 justify-center items-center">
                <h2 class="text-4xl font-bold writing-mode-vertical rotate-270 text-gray-800 tracking-wider whitespace-nowrap transition-all duration-1000 ease-[cubic-bezier(0.68,-0.55,0.27,1.55)]" 
                    class:opacity-0={!isVisible}
                    class:translate-x-[-20px]={!isVisible}
                    class:opacity-100={isVisible}
                    class:translate-x-0={isVisible}>
                    О ПРОГРАММЕ
                </h2>
            </div>
            
            <div class="lg:hidden mb-6 text-center">
                <h2 class="text-3xl font-bold text-gray-800 tracking-wider transition-all duration-1000 ease-out"
                    class:opacity-0={!isVisible}
                    class:translate-y-[-20px]={!isVisible}
                    class:opacity-100={isVisible}
                    class:translate-y-0={isVisible}>
                    О ПРОГРАММЕ
                </h2>
            </div>
            
            <div class="flex-1 flex flex-col lg:flex-row gap-6 md:gap-8">
                <div class="lg:w-1/2 transition-all duration-1000 ease-out delay-150"
                    class:opacity-0={!isVisible}
                    class:translate-y-4={!isVisible}
                    class:opacity-100={isVisible}
                    class:translate-y-0={isVisible}>
                    <div class="mb-4 md:mb-6 flex justify-center lg:justify-start items-center gap-4 md:gap-6">
                        <img src={prioritetLogo} alt="Приоритет лого" class="h-16 md:h-20 w-auto opacity-90 hover:opacity-100 transition-opacity duration-300"/>
                    </div>
      
                    <p class="text-base md:text-lg lg:text-xl leading-relaxed text-gray-700 mb-4 md:mb-6">
                        Программа развития позволяет сконцентрировать ресурсы для
                        обеспечения вклада российских университетов в достижение национальных
                        целей развития Российской Федерации на период до 2030 года.
                        Инновационные подходы и междисциплинарные исследования создают основу
                        для прорывных технологий и подготовки специалистов нового поколения.
                    </p>
      
                    <div class="mb-6 md:mb-8 flex justify-center lg:justify-start">
                        <img src={ministryLogo} alt="Министерство" class="h-14 md:h-16 w-auto opacity-80 hover:opacity-100 transition-opacity duration-300"/>
                    </div>
                </div>
      
                <div class="lg:w-1/2 flex items-center transition-all duration-1000 ease-out delay-300"
                    class:opacity-0={!isVisible}
                    class:translate-y-4={!isVisible}
                    class:opacity-100={isVisible}
                    class:translate-y-0={isVisible}>
                    <div class="w-full bg-white p-4 sm:p-6 rounded-xl shadow-md sm:shadow-lg border-l-4 border-blue-500 hover:shadow-xl transition-all duration-300">
                        <h3 class="text-xl sm:text-2xl font-bold mb-3 sm:mb-4 text-blue-600 uppercase tracking-wider text-center">Цель программы</h3>
                        <p class="text-base sm:text-lg lg:text-xl text-gray-700 leading-relaxed text-center">
                            Сформировать широкую группу университетов, которые станут лидерами
                            в создании нового научного знания, технологий и разработок для
                            внедрения в российскую экономику и социальную сферу.
                        </p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</section>

<style>
    [class*="transition-all"] {
        transition-property: all;
        will-change: transform, opacity;
    }

    @media (max-width: 640px) {
        .writing-mode-vertical {
            writing-mode: horizontal-tb;
            transform: none;
        }
    }
</style>