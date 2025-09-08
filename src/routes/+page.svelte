<script>
    import img_sekhmych_art from '$lib/assets/img/sekhmych_art.png';
    import img_sekhmych_real from '$lib/assets/img/sekhmych_real.png';
    import img_android from '$lib/assets/img/android.png';
    import img_api from '$lib/assets/img/api.png';
    import img_db from '$lib/assets/img/db.png';
    import img_email from '$lib/assets/img/email.png';
    import img_guess_app from '$lib/assets/img/guess_app.png';
    import img_meditation_app from '$lib/assets/img/meditation_app.png';
    import img_skills from '$lib/assets/img/skills.png';
    import img_tg from '$lib/assets/img/tg.png';
    import img_vk from '$lib/assets/img/vk.png';
    import img_weather_app from '$lib/assets/img/weather_app.png';
    import img_web from '$lib/assets/img/web.png';
</script>

<div>
    <!--Начало-->
    <div class="text-center w-full">
        <h2 class="text-5xl mt-6">ПОРТФОЛИО</h2>
    </div>

    <!--Вступительное-->
    <div class="flex items-center justify-center justify-items-center mt-12 space-x-28">
        <img src={img_sekhmych_art} alt="">
        <h2 class="text-5xl text-right"><b class="text-purple-500">Сергеев</b> Владимир<br><b class="text-purple-500">Веб-разработчик</b></h2>
        <img src={img_sekhmych_real} alt="">
    </div>

    <!--Мои специализации-->
    <div class="items-center justify-items-center mt-56">
        <h2 class="text-5xl text-center">МОИ СПЕЦИАЛИЗАЦИИ</h2>
        <p class="text-center w-[56rem]">Я специалист с опытом разработки веб и мобильных приложений. Я люблю изучать новые технологии. Мне нравится вникать в требования к проекту и очень эффективно дополнять их современными технологиями.</p>

        <div class="grid grid-cols-2 gap-0 mt-16 space-x-16">
            <div class="justify-items-center font-bold">
                <img src={img_android} alt="">
                <h5 class="text-center">Андроид-разработчик<br>(junior)</h5>
            </div>
            <div class="justify-items-center font-bold">
                <img src={img_api} alt="">
                <h5 class="text-center">Инженер по разработке API<br>(junior)</h5>
            </div>
            <div class="justify-items-center font-bold">
                <img src={img_web} alt="">
                <h5 class="text-center">Веб-разработчик<br>(junior)</h5>
            </div>
            <div class="justify-items-center font-bold">
                <img src={img_db} alt="">
                <h5 class="text-center">Администратор баз данных<br>(junior)</h5>
            </div>
        </div>
    </div>

    <!--Мои работы-->
    <div class="mt-24 items-center justify-items-center">
        <h2 class="text-5xl text-center">МОИ РАБОТЫ</h2>
        <p class="text-center w-[56rem]">Важно развивать в себе хорошую трудовую этику. Проявляйте себя во всем, чем бы вы ни занимались, будь то уборщик или ваша первая летняя работа, потому что эта трудовая этика будет отражаться на всем, что вы делаете в жизни.</p>
        
        <div class="flex text-center justify-items-center items-center justify-center space-x-8 mt-8">
            <div class="bg-green-400 w-64 h-96 rounded-2xl">
                <img src={img_weather_app} alt="">
                <h5 class="font-bold text-lg">Погодное приложение на Андроид</h5>
            </div>
            <div class="bg-green-400 w-64 h-96 rounded-2xl">
                <img src={img_meditation_app} alt="">
                <h5 class="font-bold text-lg">Приложение для медитации на Андроид</h5>
            </div>
            <div class="bg-green-400 w-64 h-96 rounded-2xl">
                <img src={img_guess_app} alt="">
                <h5 class="font-bold text-lg">Угадай число на Андроид</h5>
            </div>
        </div>
    </div>

    <!--Что я умею-->
    <div class="what-i-can-do mt-24 items-center justify-center justify-items-center">
        <h2 class="text-5xl text-center">ЧТО Я УМЕЮ</h2>
        <p class="text-center w-[56rem]">Единственный, с кем вам следует сравнивать себя, - это вы сами. Ваша миссия - стать сегодня лучше, чем вы были вчера. Вы делаете это, сосредоточившись на том, что вы можете сделать сегодня, чтобы совершенствоваться и расти.</p>
        <img class="w-[56rem]" src={img_skills} alt="">
    </div>

    <!--Конец-->
    <div class="w-full mt-24">
        <h2 class="text-5xl text-center">ГОТОВ К НАЙМУ</h2>
        <div class="flex items-center justify-items-center justify-center space-x-4 mt-12">
            <a class="bg-green-400 w-16 h-16" href="//vk.com/sekhmych"><img class="w-12" src={img_vk} alt=""></a>
            <a class="bg-green-400 w-16 h-16" href="//t.me/sekhmych"><img class="w-12" src={img_tg} alt=""></a>
            <a class="bg-green-400 w-16 h-16" href="mailto:sekhmych@icloud.com"><img class="w-12" src={img_email} alt=""></a>
        </div>
        <h2 class="text-5xl text-center mt-12">НАПИШИТЕ МНЕ СЕЙЧАС</h2>
    </div>

</div>


<style>
    html {
        background: aliceblue;
    }
</style>
