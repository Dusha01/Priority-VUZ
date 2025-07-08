<script>
    import prioritetLogo from '../assets/logo/priority.png'
    import ministryLogo from '../assets/logo/ministry.png'
</script>

<section id="about" class="py-24 bg-gradient-to-br from-gray-50 to-gray-100">
    <div class="container mx-auto px-4 h-full">
        <div class="flex flex-col lg:flex-row gap-8 lg:gap-16 items-stretch h-full">
            <div class="lg:w-24 flex justify-center items-center"> 
                <h2 class="text-4xl font-bold writing-mode-vertical lg:writing-mode-vertical rotate-270 text-gray-800 tracking-wider whitespace-nowrap"> 
                    О ПРОГРАММЕ
                </h2>
            </div>
            
            <div class="flex-1 flex flex-col lg:flex-row gap-8">
                <div class="lg:w-1/2">
                    <div class="mb-6 flex items-center gap-6">
                        <img src={prioritetLogo} alt="Приоритет лого" class="h-25 w-auto opacity-90 hover:opacity-100 transition-opacity" />
                    </div>
                    
                    <p class="text-lg md:text-xl leading-relaxed text-gray-700 mb-6">
                        Программа развития позволяет сконцентрировать ресурсы для обеспечения вклада российских
                        университетов в достижение национальных целей развития Российской Федерации
                        на период до 2030 года. Инновационные подходы и междисциплинарные исследования создают основу 
                        для прорывных технологий и подготовки специалистов нового поколения.
                    </p>
                    
                    <div class="mb-8">
                        <img src={ministryLogo} alt="Министерство" class="h-16 w-auto opacity-80 hover:opacity-100 transition-opacity" />
                    </div>
                </div>
                
                <div class="lg:w-1/2 flex items-center justify-center">
                    <div class="w-full bg-white p-6 rounded-xl shadow-lg border-l-4 border-blue-500 hover:shadow-xl transition-shadow">
                        <h3 class="text-2xl font-bold mb-4 text-blue-600 uppercase tracking-wider text-center">Цель программы</h3>
                        <p class="text-xl text-gray-700 leading-relaxed text-center">
                            Сформировать широкую группу университетов, которые станут лидерами в создании нового
                            научного знания, технологий и разработок для внедрения в российскую экономику и социальную сферу.
                        </p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</section>

