<script>
    import code from "../images/me.png"
    import {onMount} from "svelte";
    let count = 1;
    let wordCount = 0;
    let letterCount = 0;
    let words = ["JavaScript FullStack Dev", "programmer", "svelte enthusiast", "human :)"]
    let currentWord = words[0];
    let typingWord = ""
    let isFilled = true;

    onMount(()=>{
        let it = setInterval(()=>{
            if(isFilled) {
                typingWord+= currentWord[letterCount]
                letterCount+=1;
                if(letterCount === currentWord.length){
                    isFilled = false;
                }
            }else{
                typingWord = typingWord.slice(0, -1)

                if(typingWord.length === 0){
                    wordCount+=1;
                    isFilled = true
                    letterCount = 0

                    if(wordCount === words.length) {
                        wordCount = 0;
                    }

                    currentWord = words[wordCount]

                }
            }
        }, 200)

        setInterval(()=>{
            count+=1;
            if(count === 4) count = 0;
        }, 500)
    })

</script>

<header class="w-screen h-screen grid grid-rows-[72px,1fr] max-w-[100vw] text-white md:items-center md:justify-center bg-[#202020]">
    <nav name="icons" class="w-full h-full px-4 flex justify-between items-center md:w-[85vw] md:mx-auto">
        <span class="flex items-center gap-x-2">
            <svg class="w-8 h-8 text-[#ff4000]" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><g fill="none"><path d="M0 0h24v24H0z"/><path fill="currentColor" d="M14.62 2.662a1.5 1.5 0 0 1 1.04 1.85l-4.431 15.787a1.5 1.5 0 0 1-2.889-.81L12.771 3.7a1.5 1.5 0 0 1 1.85-1.039ZM7.56 6.697a1.5 1.5 0 0 1 0 2.12L4.38 12l3.182 3.182a1.5 1.5 0 1 1-2.122 2.121L1.197 13.06a1.5 1.5 0 0 1 0-2.12l4.242-4.243a1.5 1.5 0 0 1 2.122 0Zm8.88 2.12a1.5 1.5 0 1 1 2.12-2.12l4.243 4.242a1.5 1.5 0 0 1 0 2.121l-4.242 4.243a1.5 1.5 0 1 1-2.122-2.121L19.621 12L16.44 8.818Z"/></g></svg>
            Typing
            {#each Array(count) as _}
                .
            {/each}
        </span>
        <!--<svg class="w-8 h-8 md:hidden" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><g fill="none"><path d="M24 0v24H0V0h24ZM12.593 23.258l-.011.002l-.071.035l-.02.004l-.014-.004l-.071-.035c-.01-.004-.019-.001-.024.005l-.004.01l-.017.428l.005.02l.01.013l.104.074l.015.004l.012-.004l.104-.074l.012-.016l.004-.017l-.017-.427c-.002-.01-.009-.017-.017-.018Zm.265-.113l-.013.002l-.185.093l-.01.01l-.003.011l.018.43l.005.012l.008.007l.201.093c.012.004.023 0 .029-.008l.004-.014l-.034-.614c-.003-.012-.01-.02-.02-.022Zm-.715.002a.023.023 0 0 0-.027.006l-.006.014l-.034.614c0 .012.007.02.017.024l.015-.002l.201-.093l.01-.008l.004-.011l.017-.43l-.003-.012l-.01-.01l-.184-.092Z"/><path fill="currentColor" d="M20 17.5a1.5 1.5 0 0 1 .144 2.993L20 20.5H4a1.5 1.5 0 0 1-.144-2.993L4 17.5h16Zm0-7a1.5 1.5 0 0 1 0 3H4a1.5 1.5 0 0 1 0-3h16Zm0-7a1.5 1.5 0 0 1 0 3H4a1.5 1.5 0 1 1 0-3h16Z"/></g></svg>-->
        <a aria-label="Github" href="https://x.com/theweekshipper"><svg xmlns="http://www.w3.org/2000/svg" class="w-8 h-8" viewBox="0 0 24 24"><mask id="lineMdGithubLoop0" width="24" height="24" x="0" y="0"><g fill="#fff"><ellipse cx="9.5" cy="9" rx="1.5" ry="1"/><ellipse cx="14.5" cy="9" rx="1.5" ry="1"/></g></mask><g fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2"><path stroke-dasharray="30" stroke-dashoffset="30" d="M12 4C13.6683 4 14.6122 4.39991 15 4.5C15.5255 4.07463 16.9375 3 18.5 3C18.8438 4 18.7863 5.21921 18.5 6C19.25 7 19.5 8 19.5 9.5C19.5 11.6875 19.017 13.0822 18 14C16.983 14.9178 15.8887 15.3749 14.5 15.5C15.1506 16.038 15 17.3743 15 18C15 18.7256 15 21 15 21M12 4C10.3317 4 9.38784 4.39991 9 4.5C8.47455 4.07463 7.0625 3 5.5 3C5.15625 4 5.21371 5.21921 5.5 6C4.75 7 4.5 8 4.5 9.5C4.5 11.6875 4.98301 13.0822 6 14C7.01699 14.9178 8.1113 15.3749 9.5 15.5C8.84944 16.038 9 17.3743 9 18C9 18.7256 9 21 9 21"><animate fill="freeze" attributeName="stroke-dashoffset" dur="0.6s" values="30;0"/></path><path stroke-dasharray="10" stroke-dashoffset="10" d="M9 19"><animate fill="freeze" attributeName="stroke-dashoffset" begin="0.7s" dur="0.2s" values="10;0"/><animate attributeName="d" dur="3s" repeatCount="indefinite" values="M9 19c-1.406 0-2.844-.563-3.688-1.188C4.47 17.188 4.22 16.157 3 15.5;M9 19c-1.406 0-3-.5-4-.5-.532 0-1 0-2-.5;M9 19c-1.406 0-2.844-.563-3.688-1.188C4.47 17.188 4.22 16.157 3 15.5"/></path></g><rect width="8" height="4" x="8" y="11" fill="currentColor" mask="url(#lineMdGithubLoop0)"><animate attributeName="y" dur="10s" keyTimes="0;0.45;0.46;0.54;0.55;1" repeatCount="indefinite" values="11;11;7;7;11;11"/></rect></svg></a>
    </nav>
    <main class="flex flex-col-reverse justify-around items-center px-4 md:flex-row md:gap-x-10 md:w-[85vw] md:mx-auto">
        <a href="mailto:florent@weekshipper.com" class="p-4 w-full rounded-md border text-[#ff4000] border-[#ff4000] flex justify-center items-center gap-x-4 md:hidden">
            <svg class="w-6 h-6" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><g fill="none"><path d="M24 0v24H0V0h24ZM12.593 23.258l-.011.002l-.071.035l-.02.004l-.014-.004l-.071-.035c-.01-.004-.019-.001-.024.005l-.004.01l-.017.428l.005.02l.01.013l.104.074l.015.004l.012-.004l.104-.074l.012-.016l.004-.017l-.017-.427c-.002-.01-.009-.017-.017-.018Zm.265-.113l-.013.002l-.185.093l-.01.01l-.003.011l.018.43l.005.012l.008.007l.201.093c.012.004.023 0 .029-.008l.004-.014l-.034-.614c-.003-.012-.01-.02-.02-.022Zm-.715.002a.023.023 0 0 0-.027.006l-.006.014l-.034.614c0 .012.007.02.017.024l.015-.002l.201-.093l.01-.008l.004-.011l.017-.43l-.003-.012l-.01-.01l-.184-.092Z"/><path fill="currentColor" d="M20 4a2 2 0 0 1 1.995 1.85L22 6v12a2 2 0 0 1-1.85 1.995L20 20H4a2 2 0 0 1-1.995-1.85L2 18V6a2 2 0 0 1 1.85-1.995L4 4h16Zm0 3.414l-6.94 6.94a1.5 1.5 0 0 1-2.12 0L4 7.414V18h16V7.414ZM18.586 6H5.414L12 12.586L18.586 6Z"/></g></svg>
            <span>Get in Touch with me</span>
        </a>
        <section id="text-container" class="w-full flex flex-col justify-center items-start text-center md:text-left gap-y-4 md:gap-10">
            <h1 class="text-3xl font-extrabold ">Hello 👋, I'm Florent, a
                <span class="text-[#ff4000] pr-1" id="typer" >
                    {typingWord}
                </span>
            </h1>
            <p class="text-lg">Full-time coder, I chose the JavaScript language and its large ecosystem to develop my applications.</p>
            <a href="mailto:florent@weekshipper.com" class="hidden md:flex md:justify-center md:items-center md:gap-x-4 md:p-4 md:w-[300px] md:rounded-md md:bg-[#ff4000] md:text-[#202020]">
                <svg class="w-6 h-6" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><g fill="none"><path d="M24 0v24H0V0h24ZM12.593 23.258l-.011.002l-.071.035l-.02.004l-.014-.004l-.071-.035c-.01-.004-.019-.001-.024.005l-.004.01l-.017.428l.005.02l.01.013l.104.074l.015.004l.012-.004l.104-.074l.012-.016l.004-.017l-.017-.427c-.002-.01-.009-.017-.017-.018Zm.265-.113l-.013.002l-.185.093l-.01.01l-.003.011l.018.43l.005.012l.008.007l.201.093c.012.004.023 0 .029-.008l.004-.014l-.034-.614c-.003-.012-.01-.02-.02-.022Zm-.715.002a.023.023 0 0 0-.027.006l-.006.014l-.034.614c0 .012.007.02.017.024l.015-.002l.201-.093l.01-.008l.004-.011l.017-.43l-.003-.012l-.01-.01l-.184-.092Z"/><path fill="currentColor" d="M20 4a2 2 0 0 1 1.995 1.85L22 6v12a2 2 0 0 1-1.85 1.995L20 20H4a2 2 0 0 1-1.995-1.85L2 18V6a2 2 0 0 1 1.85-1.995L4 4h16Zm0 3.414l-6.94 6.94a1.5 1.5 0 0 1-2.12 0L4 7.414V18h16V7.414ZM18.586 6H5.414L12 12.586L18.586 6Z"/></g></svg>
                <span>Get in Touch with me</span>
            </a>
        </section>
        <section id="img-container">
            <img class="h-[65vw] w-[65vw] md:max-h-[512px]  md:max-w-lg object-cover " src={code} alt="person coding" />
        </section>
    </main>
</header>

<style>
    * {
        font-family: 'Outfit Variable', sans-serif;
    }
    #typer {
        animation: blink-caret 1s step-end infinite;
        border-right: .10em solid #ff4000
    }
    @keyframes blink-caret {
        from, to { border-color: transparent }
        50% { border-color: #ff4000 }
    }
</style>