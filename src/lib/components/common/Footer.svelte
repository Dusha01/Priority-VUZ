<script lang="ts">
    import vuzLogo from '../../assets/logo/dvgups.png';
</script>

<section
        id = "contacts"
        class="py-12 bg-gray-300">
    <div class="container mx-auto px-10 flex flex-col md:flex-row gap-8">
        <div class="flex-shrink-0">
            <a href="https://dvgups.ru/" target="_blank" rel="noopener noreferrer">
                <img 
                    src={vuzLogo} 
                    alt="DVGUPS Logo" 
                    class="w-70 h-32 object-contain"
                />
            </a>
        </div>

        <div class="flex-grow">
            <div class="mb-4">
                <a 
                    href="https://dvgups.ru/" 
                    target="_blank" 
                    rel="noopener noreferrer"
                    class="text-xl font-bold hover:underline"
                >
                    Дальневосточный государственный университет путей сообщения
                </a>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                <div>
                    <p class="mb-2">Россия, 680021, г. Хабаровск, ул. Серышева, д. 47</p>
                    <div class="flex flex-col space-y-1">
                        <a href="tel:+74212407200" class="hover:underline">+7 (4212) 407-200</a>
                        <a href="tel:+74212407516" class="hover:underline">+7 (4212) 407-516</a>
                    </div>
                </div>

                <div>
                    <p class="mb-2">
                        Координатор программы стратегического академического лидерства "Приоритет 2030" –
                        Проектный&nbsp;офис,&nbsp;ауд.&nbsp;145а
                    </p>
                    <a href="tel:+74212407581" class="hover:underline">+7 (4212) 407-581</a>
                </div>
            </div>
        </div>
    </div>
</section>