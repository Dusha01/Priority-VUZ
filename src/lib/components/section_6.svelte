<script lang="ts">
    import { onMount } from "svelte";
    import documentIcon from '../assets/icons/document.png'
    import { goto } from "$app/navigation";
    
    type DocumentItem = {
        href: string;
        text: string;
    }

    type ReportItem = {
        href: string;
        text: string;
        icon: string;
    }

    let isDropdownOpen = false;
    let sectionRef: HTMLElement | null = null;
    let isVisible = false;

    const localDocuments: DocumentItem[] = [
        {href: "https://dvgups.ru/prioritet-2030-dalnij-vostok/img/documents/pro_io58v2.pdf", text: "Инструкция ДВГУПС И 058 О дорожной карте проекта"},
        {href: "https://dvgups.ru/prioritet-2030-dalnij-vostok/img/documents/%D0%98%D0%BD%D1%81%D1%82%D1%80%D1%83%D0%BA%D1%86%D0%B8%D1%8F%20%D0%98%20060%20%D0%9E%20%D0%BA%D0%BE%D0%BC%D0%B0%D0%BD%D0%B4%D0%B8%D1%80%D0%BE%D0%B2%D0%BA%D0%B0%D1%85.pdf", text: "Инструкция ДВГУПС И 060 О командировках"},
        {href: "https://dvgups.ru/prioritet-2030-dalnij-vostok/img/documents/%D0%A0%D0%B5%D0%B3%D0%BB%D0%B0%D0%BC%D0%B5%D0%BD%D1%82%20%D0%A0%2001-23-24.pdf", text: "Регламент ДВГУПС Р 01-23-24 О проектной деятельности"},
        {href: "https://dvgups.ru/prioritet-2030-dalnij-vostok/img/documents/%D0%A0%2004-09-24%20%D0%A0%D0%B5%D0%B3%D0%BB%D0%B0%D0%BC%D0%B5%D0%BD%D1%82%20%D0%BC%D0%BE%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D0%B8.pdf", text: "Регламент ДВГУПС Р 04-09-24 О мотивации"},
        {href: "https://dvgups.ru/prioritet-2030-dalnij-vostok/%D0%9F%2001-06-23%20%D0%9E%20%D0%9A%D0%BE%D0%BE%D1%80%D0%B4%D0%B8%D0%BD%D0%B0%D1%86%D0%B8%D0%BE%D0%BD%D0%BD%D0%BE%D0%BC%20%D1%81%D0%BE%D0%B2%D0%B5%D1%82%D0%B5.pdf", text: "Положение П 01-06-23 О Координационном совете"},
        {href: "https://dvgups.ru/prioritet-2030-dalnij-vostok/img/documents/%D0%9F%2001-07-25%20%D0%9E%20%D0%BF%D1%80%D0%BE%D0%B5%D0%BA%D1%82%D0%BD%D0%BE%D0%BC%20%D0%BA%D0%BE%D0%BC%D0%B8%D1%82%D0%B5%D1%82%D0%B5%20(%D1%80%D0%B5%D0%B4%D0%B0%D0%BA%D1%86%D0%B8%D1%8F%201.0).pdf", text: "Положение П 01-07-25 О проектном комитете"},
    ];

    const reports: ReportItem[] = [
        { href: "https://dvgups.ru/prioritet-2030-dalnij-vostok/img/documents/%D0%93%D0%BE%D0%B4%D0%BE%D0%B2%D0%BE%D0%B9%20%D0%BE%D1%82%D1%87%D1%91%D1%82%20%D0%B7%D0%B0%202023%20%D0%B3%D0%BE%D0%B4%20%D0%9F%D1%80%D0%B8%D0%BE%D1%80%D0%B8%D1%82%D0%B5%D1%82-2030.pdf", text: "Отчёт 2023", icon: documentIcon },
        { href: "https://dvgups.ru/prioritet-2030-dalnij-vostok/img/documents/%D0%9E%D1%82%D1%87%D1%91%D1%82%20%D0%BE%20%D1%80%D0%B5%D0%B0%D0%BB%D0%B8%D0%B7%D0%B0%D1%86%D0%B8%D0%B8%20%D0%BF%D1%80%D0%BE%D0%B3%D1%80%D0%B0%D0%BC%D0%BC%D1%8B%20%D1%80%D0%B0%D0%B7%D0%B2%D0%B8%D1%82%D0%B8%D1%8F%20%D0%B7%D0%B0%202024%20%D0%B3%D0%BE%D0%B4.pdf", text: "Отчёт 2024", icon: documentIcon }
    ];

    const toggleDropdown = () => {
        isDropdownOpen = !isDropdownOpen;
    };

    const openProjectPage = () => {
        console.log("Opening project page");
    };

    const openProposalForm = () => {
        window.open('https://forms.yandex.ru/u/65adc190c09c0298cfc3690e/?iframe=1', '_blank');;
    };

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
    id="documents-section" 
    class="py-12 bg-gray-100"
    bind:this={sectionRef}>

    <div class="container mx-auto px-4">
        <div class="mb-8 transition-all duration-700 ease-out"
            class:opacity-0={!isVisible}
            class:translate-y-10={!isVisible}
            class:opacity-100={isVisible}
            class:translate-y-0={isVisible}>
            <a href="https://dvgups.ru/prioritet-2030-dalnij-vostok/DevelopmentProgramV3.pdf" target="_blank" class="group">
                <div class="page-bottom_div bg-white p-4 rounded-lg shadow-md hover:shadow-lg transition-shadow duration-300 border-l-4 border-blue-500">
                    <p class="text-lg font-medium text-gray-800 group-hover:text-blue-600 transition-colors duration-300">
                        Программа развития университета
                    </p>
                </div>
            </a>
        </div>

        <div class="mb-8 transition-all duration-700 ease-out delay-100"
            class:opacity-0={!isVisible}
            class:translate-y-10={!isVisible}
            class:opacity-100={isVisible}
            class:translate-y-0={isVisible}>
            <div class="relative">
                <button 
                    on:click={toggleDropdown}
                    class="w-full bg-blue-600 text-white py-3 px-6 rounded-lg text-left font-medium hover:bg-blue-700 transition-colors duration-300 flex justify-between items-center">
                    <span>Локальные нормативные акты проектной деятельности</span>
                    <svg 
                        class={`w-5 h-5 ml-2 transition-transform duration-300 ${isDropdownOpen ? 'transform rotate-180' : ''}`} 
                        fill="none" 
                        stroke="currentColor" 
                        viewBox="0 0 24 24" 
                        xmlns="http://www.w3.org/2000/svg">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"></path>
                    </svg>
                </button>

                <div class="mt-1 overflow-hidden transition-all duration-300 ease-out"
                    class:max-h-0={!isDropdownOpen}
                    class:max-h-[500px]={isDropdownOpen}>
                    <div class="bg-white rounded-md shadow-lg z-50 border border-gray-200 w-full">
                        {#each localDocuments as doc}
                            <a href={doc.href} target="_blank" class="group block">
                                <div class="p-4 hover:bg-gray-50 transition-colors duration-200 border-b border-gray-100 last:border-b-0">
                                    <p class="text-gray-700 group-hover:text-blue-600 transition-colors duration-300">
                                        {doc.text}
                                    </p>
                                </div>
                            </a>
                        {/each}
                    </div>
                </div>
            </div>
        </div>

        <div class="mb-8 transition-all duration-700 ease-out delay-200"
            class:opacity-0={!isVisible}
            class:translate-y-10={!isVisible}
            class:opacity-100={isVisible}
            class:translate-y-0={isVisible}>
            <button 
                on:click={() => goto('/Provisions')}
                class="dropbtn2 w-full bg-blue-600 text-white py-3 px-6 rounded-lg text-left font-medium hover:bg-blue-700 transition-colors duration-300">
                Положения о реализуемых проектах
            </button>
        </div>

        <div class="mb-8 transition-all duration-700 ease-out delay-300"
            class:opacity-0={!isVisible}
            class:translate-y-10={!isVisible}
            class:opacity-100={isVisible}
            class:translate-y-0={isVisible}>
            <button 
                on:click={openProposalForm}
                class="btn w-full bg-green-600 text-white py-3 px-6 rounded-lg font-medium hover:bg-green-700 transition-colors duration-300">
                Проектное предложение
            </button>
        </div>

        <div class="reports transition-all duration-700 ease-out delay-400"
            class:opacity-0={!isVisible}
            class:translate-y-10={!isVisible}
            class:opacity-100={isVisible}
            class:translate-y-0={isVisible}>
            <h3 class="text-2xl font-bold text-gray-800 mb-6">Отчеты</h3>
            <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                {#each reports as report}
                    <a href={report.href} target="_blank" class="group">
                        <div class="reports__item bg-white p-4 rounded-lg shadow-md hover:shadow-lg transition-shadow duration-300 flex items-center">
                            <img src={report.icon} alt="Document" class="w-10 h-10 mr-4">
                            <span class="text-gray-800 font-medium group-hover:text-blue-600 transition-colors duration-300">
                                {report.text}
                            </span>
                        </div>
                    </a>
                {/each}
            </div>
        </div>
    </div>
</section>

<style>
    [class*="transition-all"] {
        transition-property: all;
        will-change: transform, opacity;
    }

    .dropdown-content {
        max-height: 400px;
        overflow-y: auto;
    }

    .dropdown-content::-webkit-scrollbar {
        width: 6px;
    }

    .dropdown-content::-webkit-scrollbar-track {
        background: #f1f1f1;
        border-radius: 10px;
    }

    .dropdown-content::-webkit-scrollbar-thumb {
        background: #888;
        border-radius: 10px;
    }

    .dropdown-content::-webkit-scrollbar-thumb:hover {
        background: #555;
    }
</style>