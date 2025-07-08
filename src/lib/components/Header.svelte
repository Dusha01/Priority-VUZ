<script lang="ts">
    import DVGUPSLogo from '../assets/dvgups.png'
    import prioritetLogo from '../assets/priority.png'
    import socialCenterLogo from '../assets/socioСenter.png'
</script>

<header class="fixed w-full z-50 bg-white shadow-md py-2">
    <div class="container mx-auto px-4">
        <div class="flex justify-between items-center">
            <div class="flex items-center space-x-4">
                <a href="https://sociocenter.info" target="_blank" rel="noopener noreferrer">
                    <img src={socialCenterLogo} alt="Социо Центр" class="h-12"/>
                </a>
                <a href="https://priority2030.ru" target="_blank" rel="noopener noreferrer">
                    <img src={prioritetLogo} alt="Приоритет 2030" class="h-12"/>
                </a>
                <a href="https://dvgups.ru/" target="_blank" rel="noopener noreferrer">
                    <img src={DVGUPSLogo} alt="ДВГУПС" class="h-12"/>
                </a>
            </div>
        </div>
    </div>
</header>