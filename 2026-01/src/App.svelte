<script>
    import { onMount } from "svelte";

    let displayText = "";
    const fullText = "why hello there :)";

    onMount(() => {
        let index = 0;
        const interval = setInterval(() => {
            if (index < fullText.length) {
                displayText += fullText[index];
                index++;
            } else {
                clearInterval(interval);
            }
        }, 150);

        return () => clearInterval(interval);
    });
</script>

<main class="flex flex-col bg-orange-100 h-screen justify-center items-center">
    <div class="md:max-w-lg shadow-lg">
        <section class="flex flex-row bg-orange-200 py-12 pr-4">
            <h1
                class="grow text-end text-black text-4xl font-bold tracking-wider"
            >
                vincentnguyen.ca
            </h1>
        </section>
        <section class="flex flex-col bg-cyan-100 py-8">
            <p
                class="grow text-center text-black text-2xl font-semibold typing-text"
            >
                {displayText}<span class="cursor">|</span>
            </p>
        </section>
        <section class="flex flex-col bg-indigo-400 p-6 space-y-4">
            <p class="text-white text-lg font-semibold">
                I'm a software engineer.
            </p>
            <p class="text-white text-lg font-semibold">
                Currently, I'm working as a frontend developer for Acre
                Security.
            </p>
            <p class="text-white text-lg font-semibold">
                I strive to build high-quality, user-friendly web applications
                that provide beautiful digital experiences.
            </p>
            <p class="text-white text-lg font-semibold">
                In my spare time, I enjoy walking my dogs, managing my home
                server, and playing video games with my friends.
            </p>
        </section>
        <section class="flex flex-row bg-pink-300 p-6 justify-between">
            <a
                class="text-black font-semibold hover:text-white"
                href="https://github.com/vincendiary">GitHub</a
            >
            <a
                class="text-black font-semibold hover:text-white"
                href="https://linkedin.com/in/vinhvn">LinkedIn</a
            >
            <a
                class="text-black font-semibold hover:text-white"
                href="mailto:vincentn337@gmail.com">Email</a
            >
            <a
                class="text-black font-semibold hover:text-white"
                href="https://media.discordapp.net/attachments/711624704456261665/1444796915148394638/image.png?ex=6953963b&is=695244bb&hm=2f51cae71b702064f691f472395ace514b028751fefe1c0d439176f732c42900&=&format=webp&quality=lossless"
                >Resume</a
            >
        </section>
    </div>
</main>

<style>
    .typing-text {
        background: linear-gradient(90deg, #1e40af, #06b6d4, #8b5cf6);
        background-size: 200% auto;
        -webkit-background-clip: text;
        background-clip: text;
        -webkit-text-fill-color: transparent;
        animation: gradient-shift 3s ease infinite;
    }

    @keyframes gradient-shift {
        0%,
        100% {
            background-position: 0% center;
        }
        50% {
            background-position: 100% center;
        }
    }

    .cursor {
        animation: blink 1s step-end infinite;
        -webkit-text-fill-color: #1e40af;
    }

    @keyframes blink {
        0%,
        50% {
            opacity: 1;
        }
        51%,
        100% {
            opacity: 0;
        }
    }
</style>
