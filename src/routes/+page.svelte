<script lang="ts">
    import img_sekhmych_art from "$lib/assets/img/sekhmych_art.png";
    import img_sekhmych_real from "$lib/assets/img/sekhmych_real.jpg";
    import img_android from "$lib/assets/img/android.png";
    import img_api from "$lib/assets/img/api.png";
    import img_db from "$lib/assets/img/db.png";
    import img_email from "$lib/assets/img/email.png";
    import img_guess_app from "$lib/assets/img/guess_app.png";
    import img_meditation_app from "$lib/assets/img/meditation_app.png";
    import img_skills from "$lib/assets/img/skills.png";
    import img_tg from "$lib/assets/img/tg.png";
    import img_vk from "$lib/assets/img/vk.png";
    import img_weather_app from "$lib/assets/img/weather_app.png";
    import img_web from "$lib/assets/img/web.png";
    import img_github from "$lib/assets/img/github.png";

    let counter = 0;

    let index = 0;
    let prof = ["Веб-разработчик", "Андроид-разработчик"];
    let cur_prof = $derived(prof[index]);

    $effect(() => {


        counter += 1;

        if (counter == 5000) {
            if (index == prof.length) {
                index = 0;
            } else {
                index += 1;
            }
        }
    });
</script>

<div class="scroll-smooth">
    <button
        onclick={() => {
            document
                .getElementById("main")
                ?.scrollIntoView({ block: "center", behavior: "smooth" });
        }}
        class="text-5xl hover:cursor-pointer hover:bg-white hover:border-2 hover:text-black transition-all fixed bottom-4 rounded-full right-4 w-16 h-16 bg-black text-white flex items-center justify-center justify-items-center"
    >
        &uarr;
    </button>

    <!--Navbar-->
    <div
        class="flex bg-black top-0 w-full text-white h-18 items-center justify-items-center justify-center"
    >
        <nav class="space-x-4">
            <!--<a class="hover:border-b-2 border-white transition-all" href="#main"
                >ГЛАВНАЯ</a
            >-->
            <a
                class="hover:border-b-2 border-white transition-all"
                href="#specializations">СПЕЦИАЛИЗАЦИИ</a
            >
            <a
                class="hover:border-b-2 border-white transition-all"
                href="#works">РАБОТЫ</a
            >
            <a
                class="hover:border-b-2 border-white transition-all"
                href="#skills">НАВЫКИ</a
            >
            <a
                class="hover:border-b-2 border-white transition-all"
                href="#contacts">КОНТАКТЫ</a
            >
        </nav>
    </div>

    <!--Начало-->
    <div id="main" class="text-center w-full mt-12">
        <h2 class="text-5xl mt-6 tracking-widest">ПОРТФОЛИО</h2>
    </div>

    <div
        class="absolute right-[-7.5rem] top-0 -z-10 blur-lg rounded-full w-96 h-96 bg-purple-500"
    ></div>
    <!--Вступительное-->
    <div
        class="flex items-center justify-center justify-items-center mt-12 space-x-28"
    >
        <img
            class="w-64 h-64 rounded-full"
            title="Автор (рисунок)"
            src={img_sekhmych_art}
            alt="Автор в виде рисунка"
        />
        <h2 class="text-5xl text-right">
            <b class="text-purple-500">Сергеев</b> Владимир<br /><b
                class="text-purple-500 text-4xl">{cur_prof}</b
            ><br /><a
                href="https://www.sakha.gov.ru/"
                target="_blank"
                class="font-light text-[2rem] hover:border-b-2 border-amber-400 transition-all"
                >&mdash;>Из Якутии</a
            >
        </h2>
        <img
            class="w-64 h-64 rounded-full"
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
            class="transition-all m-auto hover:cursor-pointer font-bold text-3xl bg-green-500 p-6 rounded-lg text-center tracking-[1.2rem] hover:bg-white hover:text-black hover:border-2 hover:border-black"
            >&darr;НИЖЕ&darr;</button
        >
    </div>

    <div
        class="absolute left-[-9.5rem] top-[46rem] -z-10 blur-lg rounded-full w-80 h-80 bg-purple-500"
    ></div>
    <!--Мои специализации-->
    <div id="specializations" class="items-center justify-items-center mt-56">
        <h2 class="text-5xl text-center">МОИ СПЕЦИАЛИЗАЦИИ</h2>
        <p class="text-center w-[56rem] mt-2">
            Я специалист с опытом разработки веб и мобильных приложений. Я люблю
            изучать новые технологии. Мне нравится вникать в требования к
            проекту и очень эффективно дополнять их современными технологиями.
        </p>

        <div
            class="grid grid-cols-2 items-center justify-center gap-x-44 gap-12 mt-16 space-x-36"
        >
            <div
                class="grid-cols-2 m-auto items-center justify-items-center font-bold"
            >
                <img
                    class="w-16 h-16"
                    title="Андроид"
                    src={img_android}
                    alt="Лого Андроид"
                />
                <h5 class="text-center">Андроид-разработчик<br />(junior)</h5>
            </div>
            <div
                class="grid-cols-2 m-auto items-center justify-items-center font-bold"
            >
                <img
                    class="w-16 h-16"
                    title="API"
                    src={img_api}
                    alt="Лого API"
                />
                <h5 class="text-center">
                    Инженер по разработке API<br />(junior)
                </h5>
            </div>
            <div
                class="grid-cols-2 m-auto items-center justify-items-center font-bold"
            >
                <img
                    class="w-16 h-16"
                    title="Веб-разработка"
                    src={img_web}
                    alt="Лого веб-разработка"
                />
                <h5 class="text-center">Веб-разработчик<br />(junior)</h5>
            </div>
            <div
                class="grid-cols-2 m-auto items-center justify-items-center font-bold"
            >
                <img
                    class="w-16 h-16"
                    title="Базы данных"
                    src={img_db}
                    alt="Лого БД"
                />
                <h5 class="text-center">
                    Администратор баз данных<br />(junior)
                </h5>
            </div>
        </div>
    </div>

    <div
        class="absolute right-[-10.5rem] top-[128rem] -z-10 blur-lg rounded-full w-80 h-80 bg-purple-500"
    ></div>
    <!--Мои работы-->
    <div id="works" class="mt-24 items-center justify-items-center">
        <h2 class="text-5xl text-center">МОИ РАБОТЫ</h2>
        <p class="text-center w-[56rem] mt-2">
            Важно развивать в себе хорошую трудовую этику. Проявляйте себя во
            всем, чем бы вы ни занимались, будь то уборщик или ваша первая
            летняя работа, потому что эта трудовая этика будет отражаться на
            всем, что вы делаете в жизни.
        </p>

        <div
            class="flex text-center justify-items-center items-center justify-center space-x-8 mt-8"
        >
            <div class="relative bg-green-400 w-64 h-96 rounded-2xl">
                <img
                    title="YakseCast"
                    src={img_weather_app}
                    alt="Погодное приложение с настройками, текущей погодой, прогнозом, и якутской культурой"
                />
                <h5 class="font-bold text-lg">
                    Погодное приложение на Андроид
                </h5>
                <div
                    class="absolute flex w-16 items-center justify-center h-16 right-0 bottom-[4rem] rounded-lg rounded-r-none bg-white"
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
            <div class="relative bg-green-400 w-64 h-96 rounded-2xl">
                <img
                    title="Meditation App"
                    src={img_meditation_app}
                    alt="Приложение с лекциями, фоновыми звуками для медитации"
                />
                <h5 class="font-bold text-lg">
                    Приложение для медитации на Андроид
                </h5>
                <div
                    class="absolute flex w-16 items-center justify-center h-16 right-0 bottom-[4rem] rounded-lg rounded-r-none bg-white"
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
            <div class="relative bg-green-400 w-64 h-96 rounded-2xl">
                <img
                    title="Guess The Number"
                    src={img_guess_app}
                    alt="Игра с уровня сложностями по угадыванию числа в определённом диапозоне"
                />
                <h5 class="font-bold text-lg">Угадай число на Андроид</h5>
                <div
                    class="absolute flex w-16 items-center justify-center h-16 right-0 bottom-[4rem] rounded-lg rounded-r-none bg-white"
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
        <h2 class="text-5xl text-center">ЧТО Я УМЕЮ</h2>
        <p class="text-center w-[56rem] mt-2">
            Единственный, с кем вам следует сравнивать себя, - это вы сами. Ваша
            миссия - стать сегодня лучше, чем вы были вчера. Вы делаете это,
            сосредоточившись на том, что вы можете сделать сегодня, чтобы
            совершенствоваться и расти.
        </p>
        <img
            title="Мои скиллы"
            class="w-[56rem]"
            src={img_skills}
            alt="Умения автора: Java; Pyhton; Kotlin; C; C++; C#; JavaScript (JS); PostMan; PyCharm; Git; VS Code; Android Studio; Visual Studio; Intellij Idea; MySql; SqLite; Firebase"
        />
    </div>

    <!--Конец-->
    <div id="contacts" class="w-full mt-24">
        <h2 class="text-5xl text-center">ГОТОВ К НАЙМУ</h2>
        <div
            class="flex items-center justify-items-center justify-center space-x-4 mt-12"
        >
            <a
                class="bg-green-400 w-16 h-16 flex rounded-lg"
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
                class="bg-green-400 w-16 h-16 flex rounded-lg"
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
                class="bg-green-400 w-16 h-16 flex rounded-lg"
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
        <h2 class="text-6xl text-center mt-12 tracking-[1.5rem]">
            НАПИШИТЕ МНЕ СЕЙЧАС
        </h2>
    </div>
</div>
