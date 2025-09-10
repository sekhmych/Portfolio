<script lang="ts">
    import img_sekhmych_art from "$lib/assets/img/sekhmych-art.png";
    import img_sekhmych_real from "$lib/assets/img/sekhmych-real.jpg";
    import img_android from "$lib/assets/img/android.png";
    import img_api from "$lib/assets/img/api.png";
    import img_db from "$lib/assets/img/db.png";
    import img_email from "$lib/assets/img/email.png";
    import img_guess_app from "$lib/assets/img/guess-app.png";
    import img_meditation_app from "$lib/assets/img/meditation-app.png";
    import img_skills from "$lib/assets/img/skills.png";
    import img_tg from "$lib/assets/img/tg.png";
    import img_vk from "$lib/assets/img/vk.png";
    import img_weather_app from "$lib/assets/img/weather-app.png";
    import img_web from "$lib/assets/img/web.png";
    import img_github from "$lib/assets/img/github.png";
    import {
        blur,
        crossfade,
        draw,
        fade,
        fly,
        scale,
        slide,
    } from "svelte/transition";

    let bg_offset_x = $state(0);
    let bg_offset_y = $state(0);

    let counter = $state(0);

    let index = $state(0);
    let prof = [
        "Веб-разработчик",
        "Инженер по разработке API",
        "Андроид-разработчик",
        "Администратор баз данных",
    ];
    let cur_prof = $derived(prof[index]);
    let interval = $state(1000);

    $effect(() => {
        setInterval(() => {
            counter += 1;

            if (counter == 5) {
                if (index == prof.length - 1) {
                    index = 0;
                } else {
                    index += 1;
                }
                counter = 0;
            }
        }, interval);
    });
</script>

<div
    onpointermove={(e) => {
        bg_offset_x = Math.round(e.clientX / (window.innerWidth / 16));
        bg_offset_y = e.clientY;
    }}
>
    <!--<div
        class="absolute left-0 top-0 bg-purple-300 rounded-full w-32 h-32"
        id="tygydyn"
    ></div>-->

    <button
        onclick={() => {
            document
                .getElementById("main")
                ?.scrollIntoView({ block: "center", behavior: "smooth" });
        }}
        class="text-5xl transition-all delay-150 duration-300 ease-in-out hover:cursor-pointer hover:bg-white hover:border-2 hover:border-black hover:text-green-400 fixed bottom-4 rounded-full right-4 w-16 h-16 bg-black text-white flex items-center justify-center justify-items-center"
    >
        &uarr;
    </button>

    <!--Navbar-->
    <div
        class="flex bg-black top-0 w-full text-white h-fit items-center justify-items-center justify-center"
    >
        <nav class="flex flex-col lg:flex lg:flex-row lg:space-x-4 lg:h-16  items-center justify-center">
            <!--<a class="hover:border-b-2 border-white transition-all" href="#main"
                >ГЛАВНАЯ</a
            >-->
            <a
                class="hover:border-b-2 hover:text-green-400 border-white transition-all duration-75 ease-in-out"
                href="#specializations">СПЕЦИАЛИЗАЦИИ</a
            >
            <a
                class="hover:border-b-2 hover:text-green-400 border-white transition-all duration-75 ease-in-out"
                href="#works">РАБОТЫ</a
            >
            <a
                class="hover:border-b-2 hover:text-green-400 border-white transition-all duration-75 ease-in-out"
                href="#skills">НАВЫКИ</a
            >
            <a
                class="hover:border-b-2 hover:text-green-400 border-white transition-all duration-75 ease-in-out"
                href="#contacts">КОНТАКТЫ</a
            >
        </nav>
    </div>

    <!--Начало-->
    <div id="main" class="text-center w-full mt-12">
        <h2 class="text-5xl mt-6 tracking-widest transition-all delay-75 duration-300 ease-in hover:tracking-[2rem]">ПОРТФОЛИО</h2>
    </div>

    <div
        class="scrollbar-hide overflow-x-hidden absolute right-[-7.5rem] top-0 -z-10 blur-lg rounded-full w-64 h-64 lg:w-96 lg:h-96 bg-purple-500"
    ></div>
    <!--Вступительное-->
    <div
        class="flex lg:flex-row flex-col items-center justify-center justify-items-center p-4 mt-12"
    >
        <img
            class="lg:w-64 lg:h-64 w-32 h-32 rounded-full transition-all delay-75 duration-300 ease-in-out hover:scale-150 hover:translate-x-8"
            title="Автор (рисунок)"
            src={img_sekhmych_art}
            alt="Автор в виде рисунка"
        />
        <h2
            class="relative cols-3 m-auto text-2xl lg:text-5xl items-center justify-center justify-items-center text-center lg:w-[36rem]"
        >
            <b class="text-purple-500">Сергеев</b> Владимир<br />
            {#key cur_prof}
                <div
                    class="absolute lg:relative m-auto text-center"
                    transition:slide
                >
                    <b class="text-purple-500 m-auto text-2xl lg:text-3xl">{cur_prof}</b>
                </div>
            {/key}
            <br /><a
                href="https://www.sakha.gov.ru/"
                target="_blank"
                class="font-light text-[1.25rem] lg:text-[2rem] hover:border-b-2 border-purple-400 transition-all duration-75 ease-in-out"
                >&mdash;>Из Якутии</a
            >
        </h2>
        <img
            class="lg:w-64 lg:h-64 w-32 h-32 rounded-full transition-all delay-75 duration-300 ease-in-out hover:scale-150 hover:-translate-x-8"
            title="Автор (в реальности)"
            src={img_sekhmych_real}
            alt="Автор. Молодой 19-летний специалист с усами"
        />
    </div>

    <div
        class="flex items-center justify-center justify-items-center w-screen mt-12"
    >
        <button
            onclick={() => {
                document
                    .getElementById("specializations")
                    ?.scrollIntoView({ block: "start", behavior: "smooth" });
            }}
            class="absolute transition-all delay-50 duration-150 ease-in-out m-auto hover:cursor-pointer font-bold text-3xl bg-green-500 p-6 rounded-lg text-center tracking-[1.2rem] hover:bg-white hover:text-black hover:border-2 hover:border-black"
            >&darr;НИЖЕ&darr;</button
        >
    </div>

    <div
        class="scrollbar-hide overflow-x-hidden absolute left-[-9.5rem] top-[46rem] -z-10 blur-lg rounded-full w-80 h-80 bg-purple-500"
    ></div>
    <!--Мои специализации-->
    <div id="specializations" class="items-center justify-items-center mt-56">
        <h2
            class="text-4xl lg:text-5xl text-center transition-all delay-150 duration-300 ease-in-out hover:scale-125"
        >
            МОИ СПЕЦИАЛИЗАЦИИ
        </h2>
        <p
            class="lg:text-2xl text-center w-fit lg:w-[56rem] mt-8 transition-all delay-150 duration-300 ease-in-out hover:scale-125 cursor-default hover:bg-black hover:text-white hover:p-2"
        >
            Я специалист с опытом разработки веб и мобильных приложений. Я люблю
            изучать новые технологии. Мне нравится вникать в требования к
            проекту и очень эффективно дополнять их современными технологиями.
        </p>

        <div
            class="grid grid-cols-2 items-center justify-center gap-x-2 lg:gap-x-44 gap-2 lg:gap-12 mt-16 space-x-4 lg:space-x-36"
        >
            <div
                class="grid-cols-2 m-auto items-center justify-items-center font-bold transition-all delay-150 duration-300 ease-in-out hover:scale-125 cursor-default"
            >
                <img
                    class="w-28 h-16"
                    title="Андроид"
                    src={img_android}
                    alt="Лого Андроид"
                />
                <h5 class="text-center text-sm lg:text-md">Андроид-разработчик<br />(junior)</h5>
            </div>
            <div
                class="grid-cols-2 m-auto items-center justify-items-center font-bold transition-all delay-150 duration-300 ease-in-out hover:scale-125 cursor-default"
            >
                <img
                    class="w-16 h-16"
                    title="API"
                    src={img_api}
                    alt="Лого API"
                />
                <h5 class="text-center text-sm lg:text-md">
                    Инженер по разработке API<br />(junior)
                </h5>
            </div>
            <div
                class="grid-cols-2 m-auto items-center justify-items-center font-bold transition-all delay-150 duration-300 ease-in-out hover:scale-125 cursor-default"
            >
                <img
                    class="w-16 h-16"
                    title="Веб-разработка"
                    src={img_web}
                    alt="Лого веб-разработка"
                />
                <h5 class="text-center text-sm lg:text-md">Веб-разработчик<br />(junior)</h5>
            </div>
            <div
                class="grid-cols-2 m-auto items-center justify-items-center font-bold transition-all delay-150 duration-300 ease-in-out hover:scale-125 cursor-default"
            >
                <img
                    class="w-16 h-16"
                    title="Базы данных"
                    src={img_db}
                    alt="Лого БД"
                />
                <h5 class="text-center text-sm lg:text-md">
                    Администратор баз данных<br />(junior)
                </h5>
            </div>
        </div>
    </div>

    <div
        class="scrollbar-hide overflow-x-hidden absolute overflow-clip right-[-10.5rem] top-[128rem] -z-10 blur-lg rounded-full w-80 h-80 bg-purple-500"
    ></div>
    <!--Мои работы-->
    <div id="works" class="mt-24 items-center justify-items-center">
        <h2
            class="text-4xl lg:text-5xl text-center transition-all delay-150 duration-300 ease-in-out hover:scale-125"
        >
            МОИ РАБОТЫ
        </h2>
        <p
            class="text-center w-fit lg:w-[56rem] mt-8 transition-all delay-150 duration-300 ease-in-out hover:scale-125 cursor-default hover:bg-black hover:text-white hover:p-2"
        >
            Важно развивать в себе хорошую трудовую этику. Проявляйте себя во
            всем, чем бы вы ни занимались, будь то уборщик или ваша первая
            летняя работа, потому что эта трудовая этика будет отражаться на
            всем, что вы делаете в жизни.
        </p>

        <div
            class="flex flex-col space-y-8 lg:space-y-0 lg:flex-row text-center justify-items-center items-center  space-x-8 mt-8"
        >
            <div
                class="group relative transition delay-75 duration-300 ease-in-out hover:scale-110 bg-green-400 w-64 h-96 rounded-2xl"
            >
                <img
                    class="w-full transition-all delay-150 duration-300 ease-in-out group-hover:translate-y-8 group-hover:scale-y-125 group-hover:rounded-2xl"
                    title="YakseCast"
                    src={img_weather_app}
                    alt="Погодное приложение с настройками, текущей погодой, прогнозом, и якутской культурой"
                />
                <h5
                    class="absolute transition-all delay-150 duration-300 ease-in-out group-hover:opacity-0 group-hover:translate-y-16 w-full font-bold text-md p-2"
                >
                    Погодное приложение на Андроид
                </h5>
                <div
                    class="absolute flex w-16 items-center justify-center h-16 right-0 bottom-[8rem] transition-all delay-150 duration-300 ease-in-out group-hover:rounded-2xl group-hover:bottom-0 rounded-lg rounded-r-none bg-green-400"
                >
                    <a href="//github.com" target="_blank">
                        <img
                            class="m-auto w-10 h-10"
                            src={img_github}
                            alt="Github"
                        />
                    </a>
                </div>
            </div>
            <div
                class="group relative transition delay-75 duration-300 ease-in-out hover:scale-110 bg-green-400 w-64 h-96 rounded-2xl"
            >
                <img
                    class="w-full transition-all delay-150 duration-300 ease-in-out group-hover:translate-y-8 group-hover:scale-y-125 group-hover:rounded-2xl"
                    title="Meditation App"
                    src={img_meditation_app}
                    alt="Приложение с лекциями, фоновыми звуками для медитации"
                />
                <h5
                    class="absolute transition-all delay-150 duration-300 ease-in-out group-hover:opacity-0 group-hover:translate-y-16 w-full font-bold text-md p-2"
                >
                    Приложение для медитации на Андроид
                </h5>
                <div
                    class="absolute flex w-16 items-center justify-center h-16 right-0 bottom-[8rem] transition-all delay-150 duration-300 ease-in-out group-hover:rounded-2xl group-hover:bottom-0 rounded-lg rounded-r-none bg-green-400"
                >
                    <a href="//github.com" target="_blank">
                        <img
                            class="m-auto w-10 h-10"
                            src={img_github}
                            alt="Github"
                        />
                    </a>
                </div>
            </div>
            <div
                class="group relative transition delay-75 duration-300 ease-in-out hover:scale-110 bg-green-400 w-64 h-96 rounded-2xl"
            >
                <img
                    class="w-full transition-all delay-150 duration-300 ease-in-out group-hover:translate-y-8 group-hover:scale-y-125 group-hover:rounded-2xl"
                    title="Guess The Number"
                    src={img_guess_app}
                    alt="Игра с уровня сложностями по угадыванию числа в определённом диапозоне"
                />
                <h5
                    class="absolute transition-all delay-150 duration-300 ease-in-out group-hover:opacity-0 group-hover:translate-y-16 text-center w-full font-bold text-md p-2"
                >
                    Угадай число на Андроид
                </h5>
                <div
                    class="absolute flex w-16 items-center justify-center h-16 right-0 bottom-[8rem] transition-all delay-150 duration-300 ease-in-out group-hover:rounded-2xl group-hover:bottom-0 rounded-lg rounded-r-none bg-green-400"
                >
                    <a href="//github.com" target="_blank">
                        <img
                            class="m-auto w-10 h-10"
                            src={img_github}
                            alt="Github"
                        />
                    </a>
                </div>
            </div>
        </div>
    </div>

    <!--Что я умею-->
    <div
        id="skills"
        class="what-i-can-do mt-24 items-center justify-center justify-items-center"
    >
        <h2
            class="text-4xl lg:text-5xl text-center transition-all delay-150 duration-300 ease-in-out hover:scale-125"
        >
            ЧТО Я УМЕЮ
        </h2>
        <p
            class="text-center w-fit lg:w-[56rem] mt-8 transition-all delay-150 duration-300 ease-in-out hover:scale-125 cursor-default hover:bg-black hover:text-white hover:p-2"
        >
            Единственный, с кем вам следует сравнивать себя, - это вы сами. Ваша
            миссия - стать сегодня лучше, чем вы были вчера. Вы делаете это,
            сосредоточившись на том, что вы можете сделать сегодня, чтобы
            совершенствоваться и расти.
        </p>
        <div
            class="flex flex-col lg:flex-row group relative transition-all delay-75 duration-300 ease-in-out"
        >
            <img
                title="Мои скиллы"
                class="w-[56rem] group-hover:opacity-0 transition-all delay-1000 duration-300 ease-in-out"
                src={img_skills}
                alt="Умения автора: Java; Pyhton; Kotlin; C; C++; C#; JavaScript (JS); PostMan; PyCharm; Git; VS Code; Android Studio; Visual Studio; Intellij Idea; MySql; SqLite; Firebase"
            />
            <h2
                class="lg:absolute w-auto opacity-100 lg:opacity-0  text-center lg:top-1/2 lg:left-1/2 lg:-translate-x-1/2 lg:-translate-y-1/2 -z-10 text-2xl lg:text-4xl  transition-all delay-[1500ms] duration-300 ease-in-out group-hover:opacity-100"
            >
                Но самый главный скилл &mdash; <p class="text-purple-500">умение изучать новое</p>
            </h2>
        </div>
    </div>

    <!--Конец-->
    <div id="contacts" class="w-full mt-24">
        <h2
            class="text-4xl lg:text-5xl text-center transition-all delay-150 duration-300 ease-in-out hover:scale-125"
        >
            ГОТОВ К НАЙМУ
        </h2>
        <div
            class="flex items-center justify-items-center justify-center space-x-4 mt-12"
        >
            <a
                class="bg-green-400 w-16 h-16 flex rounded-lg transition-all delay-150 duration-300 ease-in-out hover:scale-110 hover:-translate-x-4 hover:-rotate-45"
                href="//vk.com/sekhmych"
                target="_blank"
                ><img
                    title="VK"
                    class="w-12 m-auto"
                    src={img_vk}
                    alt="ВК профиль автора"
                /></a
            >
            <a
                class="bg-green-400 w-16 h-16 flex rounded-lg transition-all delay-150 duration-300 ease-in-out hover:scale-110 hover:-translate-y-6"
                href="//t.me/sekhmych"
                target="_blank"
                ><img
                    title="TG"
                    class="w-12 m-auto"
                    src={img_tg}
                    alt="ТГ автора"
                /></a
            >
            <a
                class="bg-green-400 w-16 h-16 flex rounded-lg transition-all delay-150 duration-300 ease-in-out hover:scale-110 hover:translate-x-4 hover:rotate-45"
                href="mailto:sekhmych@icloud.com"
                target="_blank"
                ><img
                    title="E-mail"
                    class="w-12 m-auto"
                    src={img_email}
                    alt="Электронная почта автора"
                /></a
            >
        </div>
        <h2
            class="text-4xl lg:text-5xl text-center mt-12 mb-24 tracking-[1.5rem] transition-all delay-150 duration-300 ease-in-out hover:scale-125"
        >
            НАПИШИТЕ МНЕ СЕЙЧАС
        </h2>
    </div>
</div>
