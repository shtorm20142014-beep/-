<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>NEXO</title>

    <script src="https://cdn.tailwindcss.com"></script>

    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Outfit:wght@400;600;800;900&display=swap" rel="stylesheet">

    <style>
        * {
            font-family: 'Outfit', sans-serif;
            -webkit-tap-highlight-color: transparent;
            user-select: none;
        }

        .bg-gradient-dynamic {
            background: linear-gradient(
                135deg,
                #e0f2fe 0%,
                #bae6fd 35%,
                #7dd3fc 70%,
                #38bdf8 100%
            );
            background-size: 200% 200%;
            animation: gradientMove 12s ease infinite;
        }

        @keyframes gradientMove {
            0% {
                background-position: 0% 50%;
            }

            50% {
                background-position: 100% 50%;
            }

            100% {
                background-position: 0% 50%;
            }
        }

        .glow-orb-1 {
            position: absolute;
            width: 350px;
            height: 350px;
            background: rgba(255, 255, 255, 0.6);
            filter: blur(90px);
            border-radius: 50%;
            top: 15%;
            left: 20%;
            z-index: 0;
            animation: floatOrb 8s ease-in-out infinite alternate;
        }

        .glow-orb-2 {
            position: absolute;
            width: 400px;
            height: 400px;
            background: rgba(14, 165, 233, 0.35);
            filter: blur(100px);
            border-radius: 50%;
            bottom: 15%;
            right: 20%;
            z-index: 0;
            animation: floatOrb 10s ease-in-out infinite alternate-reverse;
        }

        @keyframes floatOrb {
            0% {
                transform: translate(0, 0) scale(1);
            }

            100% {
                transform: translate(30px, -40px) scale(1.1);
            }
        }

        .nexo-title {
            background: linear-gradient(
                135deg,
                #0f172a 0%,
                #0284c7 50%,
                #0369a1 100%
            );

            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;

            text-shadow: 0 10px 30px rgba(14, 165, 233, 0.25);
        }

        .glass-card {
            background: rgba(255, 255, 255, 0.65);

            backdrop-filter: blur(16px);
            -webkit-backdrop-filter: blur(16px);

            border: 1.5px solid rgba(255, 255, 255, 0.85);

            box-shadow:
                0 10px 30px -5px rgba(14, 165, 233, 0.12),
                0 4px 12px -2px rgba(0, 0, 0, 0.03);

            transition: all 0.25s cubic-bezier(0.34, 1.56, 0.64, 1);

            display: flex;
            align-items: center;
            justify-content: space-between;

            text-decoration: none;
            cursor: pointer;
        }

        .glass-card:hover {
            transform: translateY(-4px) scale(1.03);

            background: rgba(255, 255, 255, 0.92);

            border-color: rgba(255, 255, 255, 1);

            box-shadow:
                0 20px 40px -10px rgba(14, 165, 233, 0.28),
                0 8px 20px -4px rgba(0, 0, 0, 0.06);
        }

        .glass-card:active {
            transform: translateY(-1px) scale(0.98);
        }
    </style>
</head>

<body class="bg-gradient-dynamic min-h-screen w-screen overflow-hidden flex items-center justify-center relative selection:bg-sky-200">

    <div class="glow-orb-1 pointer-events-none"></div>
    <div class="glow-orb-2 pointer-events-none"></div>

    <main class="relative z-10 w-full max-w-md px-6 flex flex-col items-center justify-center text-center my-auto">

        <header class="mb-10 sm:mb-12">

            <h1 class="nexo-title text-6xl sm:text-7xl font-extrabold tracking-widest uppercase select-none drop-shadow-sm">
                NEXO
            </h1>

            <div class="h-1.5 w-14 bg-sky-500/40 rounded-full mx-auto mt-3"></div>

        </header>

        <nav class="w-full flex flex-col gap-4 sm:gap-5" aria-label="Social Links">

            <!-- TikTok -->
            <a
                href="https://www.tiktok.com/@nex1oo"
                target="_blank"
                rel="noopener noreferrer"
                class="glass-card group w-full p-4 sm:p-4.5 rounded-2xl text-slate-800 text-lg font-semibold tracking-wide"
            >

                <div class="flex items-center gap-4 pointer-events-none">

                    <div class="w-12 h-12 rounded-xl bg-black text-white flex items-center justify-center shadow-md transition-transform group-hover:scale-110 duration-300">

                        <svg class="w-6 h-6 fill-current" viewBox="0 0 24 24">

                            <path d="M19.589 6.686a4.793 4.793 0 0 1-3.77-4.245V2h-3.445v13.672a2.896 2.896 0 0 1-2.901 2.837 2.89 2.89 0 0 1-2.888-2.887 2.89 2.89 0 0 1 2.888-2.887c.338 0 .66.058.961.16v-3.53a6.38 6.38 0 0 0-.961-.073 6.333 6.333 0 0 0-6.333 6.333 6.333 6.333 0 0 0 6.333 6.333 6.333 6.333 0 0 0 6.333-6.333V9.231a8.232 8.232 0 0 0 4.887 1.583V7.35a4.78 4.78 0 0 1-1.107-.664z"/>

                        </svg>

                    </div>

                    <span class="group-hover:text-black transition-colors">
                        TikTok
                    </span>

                </div>

                <div class="text-slate-400 group-hover:text-black transition-all group-hover:translate-x-1 pr-2 pointer-events-none">

                    <svg class="w-5 h-5 stroke-current stroke-2 fill-none" viewBox="0 0 24 24">

                        <path
                            stroke-linecap="round"
                            stroke-linejoin="round"
                            d="M8.25 4.5l7.5 7.5-7.5 7.5"
                        />

                    </svg>

                </div>

            </a>


            <!-- YouTube -->
            <a
                href="https://www.youtube.com/@nexoow"
                target="_blank"
                rel="noopener noreferrer"
                class="glass-card group w-full p-4 sm:p-4.5 rounded-2xl text-slate-800 text-lg font-semibold tracking-wide"
            >

                <div class="flex items-center gap-4 pointer-events-none">

                    <div class="w-12 h-12 rounded-xl bg-red-600 text-white flex items-center justify-center shadow-md transition-transform group-hover:scale-110 duration-300">

                        <svg class="w-6 h-6 fill-current" viewBox="0 0 24 24">

                            <path d="M23.498 6.186a3.016 3.016 0 0 0-2.122-2.136C19.505 3.545 12 3.545 12 3.545s-7.505 0-9.377.505A3.017 3.017 0 0 0 .502 6.186C0 8.07 0 12 0 12s0 3.93.502 5.814a3.016 3.016 0 0 0 2.122 2.136c1.871.505 9.376.505 9.376.505s7.505 0 9.377-.505a3.015 3.015 0 0 0 2.122-2.136C24 15.93 24 12 24 12s0-3.93-.502-5.814zM9.545 15.568V8.432L15.818 12l-6.273 3.568z"/>

                        </svg>

                    </div>

                    <span class="group-hover:text-red-600 transition-colors">
                        YouTube
                    </span>

                </div>

                <div class="text-slate-400 group-hover:text-red-600 transition-all group-hover:translate-x-1 pr-2 pointer-events-none">

                    <svg class="w-5 h-5 stroke-current stroke-2 fill-none" viewBox="0 0 24 24">

                        <path
                            stroke-linecap="round"
                            stroke-linejoin="round"
                            d="M8.25 4.5l7.5 7.5-7.5 7.5"
                        />

                    </svg>

                </div>

            </a>


            <!-- Telegram -->
            <a
                href="https://t.me/nexoowo"
                target="_blank"
                rel="noopener noreferrer"
                class="glass-card group w-full p-4 sm:p-4.5 rounded-2xl text-slate-800 text-lg font-semibold tracking-wide"
            >

                <div class="flex items-center gap-4 pointer-events-none">

                    <div class="w-12 h-12 rounded-xl bg-sky-500 text-white flex items-center justify-center shadow-md transition-transform group-hover:scale-110 duration-300">

                        <svg class="w-6 h-6 fill-current" viewBox="0 0 24 24">

                            <path d="M11.944 0A12 12 0 0 0 0 12a12 12 0 0 0 12 12 12 12 0 0 0 12-12A12 12 0 0 0 12 0a12 12 0 0 0-.056 0zm4.962 7.224c.1-.002.321.023.465.14a.506.506 0 0 1 .171.325c.016.093.036.306.02.472-.18 1.898-.962 6.502-1.36 8.627-.168.9-.499 1.201-.82 1.23-.696.065-1.225-.46-1.9-.902-1.056-.693-1.653-1.124-2.678-1.8-1.185-.78-.417-1.21.258-1.91.177-.184 3.247-2.977 3.307-3.23.007-.032.014-.15-.056-.212s-.174-.041-.249-.024c-.106.024-1.793 1.14-5.061 3.345-.48.33-.913.49-1.302.48-.428-.008-1.252-.241-1.865-.44-.752-.245-1.349-.374-1.297-.789.027-.216.325-.437.893-.663 3.498-1.524 5.831-2.529 6.998-3.014 3.332-1.386 4.025-1.627 4.476-1.635z"/>

                        </svg>

                    </div>

                    <span class="group-hover:text-sky-600 transition-colors">
                        Telegram
                    </span>

                </div>

                <div class="text-slate-400 group-hover:text-sky-600 transition-all group-hover:translate-x-1 pr-2 pointer-events-none">

                    <svg class="w-5 h-5 stroke-current stroke-2 fill-none" viewBox="0 0 24 24">

                        <path
                            stroke-linecap="round"
                            stroke-linejoin="round"
                            d="M8.25 4.5l7.5 7.5-7.5 7.5"
                        />

                    </svg>

                </div>

            </a>

        </nav>

    </main>

</body>
</html>
