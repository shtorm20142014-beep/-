```html
<!DOCTYPE html>
<html lang="ru" class="dark scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ᴢᴇɴɪᴛʜ — Аниме Онлайн</title>
    
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    
    <!-- Font Awesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <!-- Google Fonts Inter & Outfit -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&family=Outfit:wght@600;700;800;900&display=swap" rel="stylesheet">

    <!-- Tailwind Configuration -->
    <script>
        tailwind.config = {
            darkMode: 'class',
            theme: {
                extend: {
                    fontFamily: {
                        sans: ['Inter', 'sans-serif'],
                        display: ['Outfit', 'sans-serif'],
                    },
                    colors: {
                        zenith: {
                            50: '#f0f3ff',
                            100: '#e1e7fe',
                            400: '#818cf8',
                            500: '#6366f1',
                            600: '#4f46e5',
                            accent: '#a855f7',
                            cyan: '#06b6d4',
                            bg: '#0b0d17',
                            card: '#121526',
                            cardHover: '#1b1e36',
                            glass: 'rgba(18, 21, 38, 0.75)'
                        }
                    },
                    boxShadow: {
                        'neon-violet': '0 0 25px -5px rgba(168, 85, 247, 0.4)',
                        'neon-indigo': '0 0 25px -5px rgba(99, 102, 241, 0.4)',
                        'neon-cyan': '0 0 25px -5px rgba(6, 182, 212, 0.4)',
                    }
                }
            }
        }
    </script>

    <!-- Custom Style Overrides & Glassmorphism -->
    <style>
        ::-webkit-scrollbar {
            width: 8px;
            height: 8px;
        }
        ::-webkit-scrollbar-track {
            background: #0b0d17;
        }
        ::-webkit-scrollbar-thumb {
            background: #1b1e36;
            border-radius: 4px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #6366f1;
        }

        .glass-header {
            background: rgba(11, 13, 23, 0.85);
            backdrop-filter: blur(16px);
            -webkit-backdrop-filter: blur(16px);
            border-bottom: 1px solid rgba(255, 255, 255, 0.08);
        }

        .glass-card {
            background: rgba(18, 21, 38, 0.7);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
            border: 1px solid rgba(255, 255, 255, 0.06);
            transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
        }

        .glass-card:hover {
            border-color: rgba(168, 85, 247, 0.4);
            transform: translateY(-5px);
            box-shadow: 0 10px 30px -10px rgba(99, 102, 241, 0.3);
        }

        .hero-banner {
            background: linear-gradient(180deg, rgba(11, 13, 23, 0.2) 0%, rgba(11, 13, 23, 0.85) 70%, #0b0d17 100%),
                        url('https://images.unsplash.com/photo-1578632767115-351597cf2477?q=80&w=1920&auto=format&fit=crop');
            background-size: cover;
            background-position: center 30%;
        }

        .text-gradient {
            background: linear-gradient(135deg, #ffffff 0%, #c7d2fe 40%, #a855f7 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .btn-gradient {
            background: linear-gradient(135deg, #6366f1 0%, #a855f7 100%);
        }

        .btn-gradient:hover {
            background: linear-gradient(135deg, #4f46e5 0%, #9333ea 100%);
        }

        .hide-scrollbar::-webkit-scrollbar {
            display: none;
        }
        .hide-scrollbar {
            -ms-overflow-style: none;
            scrollbar-width: none;
        }
    </style>
</head>
<body class="bg-zenith-bg text-gray-100 font-sans antialiased min-h-screen flex flex-col selection:bg-zenith-accent selection:text-white">

    <!-- Top Navigation Header -->
    <header class="fixed top-0 left-0 right-0 z-50 glass-header">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex items-center justify-between h-20 gap-4">
                
                <!-- Logo -->
                <a href="#" onclick="switchMainTab('home')" class="flex items-center gap-2 group">
                    <div class="w-10 h-10 rounded-xl btn-gradient flex items-center justify-center text-white font-black text-xl shadow-neon-indigo group-hover:scale-105 transition-transform">
                        <i class="fa-solid fa-play text-sm"></i>
                    </div>
                    <span class="text-2xl font-display font-black tracking-widest text-gradient">
                        ᴢᴇɴɪᴛʜ
                    </span>
                </a>

                <!-- Desktop Navigation Links -->
                <nav class="hidden md:flex items-center space-x-1 lg:space-x-2">
                    <button onclick="switchMainTab('home')" id="nav-home" class="nav-btn px-3.5 py-2 rounded-xl text-sm font-semibold text-white bg-white/10 transition-all">Главная</button>
                    <button onclick="switchMainTab('anime')" id="nav-anime" class="nav-btn px-3.5 py-2 rounded-xl text-sm font-semibold text-gray-300 hover:text-white hover:bg-white/5 transition-all">Аниме</button>
                    <button onclick="filterOngoing()" id="nav-ongoings" class="nav-btn px-3.5 py-2 rounded-xl text-sm font-semibold text-gray-300 hover:text-white hover:bg-white/5 transition-all flex items-center gap-1.5">
                        <span class="w-2 h-2 rounded-full bg-emerald-500 animate-pulse"></span>
                        Онгоинги
                    </button>
                    <a href="#genres" class="nav-btn px-3.5 py-2 rounded-xl text-sm font-semibold text-gray-300 hover:text-white hover:bg-white/5 transition-all">Жанры</a>
                    <button onclick="switchMainTab('favorites')" id="nav-favorites" class="nav-btn px-3.5 py-2 rounded-xl text-sm font-semibold text-gray-300 hover:text-white hover:bg-white/5 transition-all flex items-center gap-2">
                        <span>Избранное</span>
                        <span id="fav-counter" class="bg-zenith-accent text-white text-xs px-2 py-0.5 rounded-full font-bold">0</span>
                    </button>
                </nav>

                <!-- Search Bar & Mobile Trigger -->
                <div class="flex items-center gap-3">
                    <div class="relative w-44 sm:w-64 lg:w-72">
                        <input type="text" id="search-input" oninput="handleSearch(this.value)" placeholder="🔍 Поиск аниме..." class="w-full bg-black/40 border border-white/10 rounded-xl px-4 py-2 pl-10 text-xs sm:text-sm text-white placeholder-gray-400 focus:outline-none focus:border-zenith-accent focus:ring-1 focus:ring-zenith-accent transition-all">
                        <i class="fa-solid fa-magnifying-glass absolute left-3.5 top-1/2 -translate-y-1/2 text-gray-400 text-xs"></i>
                        <button id="clear-search" onclick="clearSearch()" class="hidden absolute right-3 top-1/2 -translate-y-1/2 text-gray-400 hover:text-white text-xs">
                            <i class="fa-solid fa-xmark"></i>
                        </button>
                    </div>

                    <!-- Mobile Hamburger -->
                    <button id="mobile-menu-btn" onclick="toggleMobileMenu()" class="md:hidden p-2.5 rounded-xl bg-white/5 border border-white/10 text-gray-300 hover:text-white">
                        <i class="fa-solid fa-bars text-lg"></i>
                    </button>
                </div>
            </div>
        </div>

        <!-- Mobile Navigation Menu Dropdown -->
        <div id="mobile-menu" class="hidden md:hidden glass-header border-b border-white/10 px-4 pt-3 pb-6 space-y-2">
            <button onclick="switchMainTab('home'); toggleMobileMenu();" class="w-full text-left px-4 py-2.5 rounded-xl text-sm font-medium text-white hover:bg-white/5">Главная</button>
            <button onclick="switchMainTab('anime'); toggleMobileMenu();" class="w-full text-left px-4 py-2.5 rounded-xl text-sm font-medium text-gray-300 hover:bg-white/5">Аниме</button>
            <button onclick="filterOngoing(); toggleMobileMenu();" class="w-full text-left px-4 py-2.5 rounded-xl text-sm font-medium text-gray-300 hover:bg-white/5 flex items-center justify-between">
                <span>Онгоинги</span>
                <span class="w-2 h-2 rounded-full bg-emerald-500 animate-pulse"></span>
            </button>
            <a href="#genres" onclick="toggleMobileMenu()" class="block px-4 py-2.5 rounded-xl text-sm font-medium text-gray-300 hover:bg-white/5">Жанры</a>
            <button onclick="switchMainTab('favorites'); toggleMobileMenu();" class="w-full text-left px-4 py-2.5 rounded-xl text-sm font-medium text-gray-300 hover:bg-white/5 flex items-center justify-between">
                <span>Избранное</span>
                <span id="fav-counter-mobile" class="bg-zenith-accent text-white text-xs px-2 py-0.5 rounded-full font-bold">0</span>
            </button>
        </div>
    </header>

    <!-- Main Content Container -->
    <main id="main-content" class="flex-grow pt-20">
        
        <!-- HOME VIEW -->
        <div id="view-home">
            <!-- Hero Banner (Басты экран) -->
            <section class="relative min-h-[85vh] flex items-center justify-center hero-banner px-4 sm:px-6 lg:px-8 border-b border-white/5">
                <!-- Ambient Visual Lights -->
                <div class="absolute top-1/3 left-10 w-96 h-96 bg-zenith-accent/20 rounded-full blur-[140px] pointer-events-none"></div>
                <div class="absolute bottom-10 right-10 w-96 h-96 bg-zenith-500/20 rounded-full blur-[140px] pointer-events-none"></div>

                <div class="max-w-5xl mx-auto text-center relative z-10 pt-10">
                    <!-- Badge -->
                    <div class="inline-flex items-center gap-2 px-4 py-2 rounded-full bg-white/10 backdrop-blur-md border border-white/15 text-xs sm:text-sm font-semibold text-zenith-400 mb-6 shadow-neon-indigo">
                        <span class="w-2.5 h-2.5 rounded-full bg-zenith-accent animate-ping"></span>
                        <span>ТОП СЕЗОНА 2026</span>
                    </div>

                    <!-- Title -->
                    <h1 class="text-6xl sm:text-7xl md:text-8xl font-display font-black tracking-tight text-gradient mb-4">
                        ᴢᴇɴɪᴛʜ
                    </h1>
                    
                    <p class="text-xl sm:text-3xl font-extrabold text-white mb-4 tracking-wide">
                        Аниме әлеміне қош келдің! ✨
                    </p>
                    
                    <p class="max-w-2xl mx-auto text-sm sm:text-base text-gray-300 font-normal mb-8 leading-relaxed">
                        Смотрите любимые аниме в высоком HD качестве, с профессиональной озвучкой (AniLibria, Jam Club) и без рекламы.
                    </p>

                    <!-- Hero Action Buttons -->
                    <div class="flex flex-col sm:flex-row items-center justify-center gap-4">
                        <button onclick="openAnimeModal(1)" class="w-full sm:w-auto btn-gradient text-white text-base font-bold px-8 py-4 rounded-xl shadow-neon-violet hover:scale-105 transition-all flex items-center justify-center gap-3">
                            <i class="fa-solid fa-play"></i>
                            <span>Смотреть сейчас →</span>
                        </button>
                        
                        <button onclick="toggleFavorite(1)" class="w-full sm:w-auto glass-card hover:bg-white/10 text-white border border-white/20 text-base font-semibold px-8 py-4 rounded-xl transition-all flex items-center justify-center gap-3">
                            <i class="fa-regular fa-bookmark text-zenith-accent"></i>
                            <span>В избранное</span>
                        </button>
                    </div>
                </div>
            </section>

            <!-- Popular Anime Section (🔥 Популярное) -->
            <section class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-16">
                <div class="flex items-center justify-between mb-8">
                    <div>
                        <h2 class="text-2xl sm:text-3xl font-display font-extrabold text-white flex items-center gap-3">
                            <span>🔥</span>
                            <span>Популярное</span>
                        </h2>
                        <p class="text-xs sm:text-sm text-gray-400 mt-1">Аниме с самым высоким рейтингом зрителей</p>
                    </div>
                    
                    <!-- Scroll Controls -->
                    <div class="flex gap-2">
                        <button onclick="scrollGrid('popular-container', -300)" class="p-2.5 rounded-xl glass-card text-gray-300 hover:text-white">
                            <i class="fa-solid fa-chevron-left"></i>
                        </button>
                        <button onclick="scrollGrid('popular-container', 300)" class="p-2.5 rounded-xl glass-card text-gray-300 hover:text-white">
                            <i class="fa-solid fa-chevron-right"></i>
                        </button>
                    </div>
                </div>

                <!-- Popular Grid / Carousel -->
                <div id="popular-container" class="flex gap-6 overflow-x-auto hide-scrollbar pb-4 scroll-smooth">
                    <!-- Dynamic rendering via JS -->
                </div>
            </section>

            <!-- Latest Updates Section (🆕 Последние обновления) -->
            <section class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-12">
                <div class="mb-8">
                    <h2 class="text-2xl sm:text-3xl font-display font-extrabold text-white flex items-center gap-3">
                        <span>🆕</span>
                        <span>Последние обновления</span>
                    </h2>
                    <p class="text-xs sm:text-sm text-gray-400 mt-1">Свежие серии, вышедшие сегодня</p>
                </div>

                <div id="updates-container" class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6">
                    <!-- Dynamic rendering via JS -->
                </div>
            </section>

            <!-- Genres Filter Section (🎭 Жанры) -->
            <section id="genres" class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-12 border-t border-white/5">
                <div class="text-center mb-8">
                    <h2 class="text-2xl sm:text-3xl font-display font-extrabold text-white flex items-center justify-center gap-3 mb-2">
                        <span>🎭</span>
                        <span>Жанры</span>
                    </h2>
                    <p class="text-xs sm:text-sm text-gray-400">Выберите жанр для фильтрации аниме</p>
                </div>

                <!-- Genre Filter Pills -->
                <div id="genres-pills" class="flex flex-wrap items-center justify-center gap-3 max-w-4xl mx-auto">
                    <!-- Dynamic pills via JS -->
                </div>
            </section>
        </div>

        <!-- CATALOG / FILTERED VIEW -->
        <div id="view-catalog" class="hidden max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-10">
            <div class="flex items-center justify-between mb-8">
                <div>
                    <h2 id="catalog-title" class="text-3xl font-display font-black text-white">Все Аниме</h2>
                    <p id="catalog-subtitle" class="text-sm text-gray-400 mt-1">Полный каталог аниме сериалов и фильмов</p>
                </div>
                <button onclick="switchMainTab('home')" class="text-sm text-zenith-400 hover:text-white flex items-center gap-2">
                    <i class="fa-solid fa-arrow-left"></i> На главную
                </button>
            </div>

            <div id="catalog-grid" class="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-4 lg:grid-cols-5 gap-6">
                <!-- Dynamic cards -->
            </div>
        </div>

        <!-- FAVORITES VIEW -->
        <div id="view-favorites" class="hidden max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-10">
            <div class="mb-8">
                <h2 class="text-3xl font-display font-black text-white flex items-center gap-3">
                    <i class="fa-solid fa-heart text-zenith-accent"></i>
                    <span>Моё Избранное</span>
                </h2>
                <p class="text-sm text-gray-400 mt-1">Аниме, которые вы сохранили для просмотра</p>
            </div>

            <div id="favorites-grid" class="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-4 lg:grid-cols-5 gap-6">
                <!-- Dynamic cards -->
            </div>

            <div id="favorites-empty" class="hidden text-center py-20 glass-card rounded-2xl max-w-xl mx-auto">
                <i class="fa-regular fa-bookmark text-5xl text-gray-600 mb-4 block"></i>
                <h3 class="text-xl font-bold text-white mb-2">Ваша коллекция пуста</h3>
                <p class="text-sm text-gray-400 mb-6">Добавляйте понравившиеся аниме в избранное, чтобы не потерять!</p>
                <button onclick="switchMainTab('home')" class="btn-gradient text-white text-sm font-bold px-6 py-3 rounded-xl shadow-neon-indigo">
                    Перейти к каталогу
                </button>
            </div>
        </div>
    </main>

    <!-- ANIME DETAIL & PLAYER MODAL (▶️ Аниме беті) -->
    <div id="anime-modal" class="fixed inset-0 z-50 flex items-center justify-center p-3 sm:p-6 bg-black/80 backdrop-blur-md hidden opacity-0 transition-opacity duration-300 overflow-y-auto">
        <div class="glass-card w-full max-w-5xl rounded-2xl border border-white/10 relative my-8 overflow-hidden shadow-2xl">
            
            <!-- Close Modal Button -->
            <button onclick="closeAnimeModal()" class="absolute top-4 right-4 z-20 w-10 h-10 rounded-full bg-black/60 hover:bg-white/20 text-white flex items-center justify-center transition-all">
                <i class="fa-solid fa-xmark text-lg"></i>
            </button>

            <!-- Modal Content Wrapper -->
            <div class="p-6 sm:p-8">
                
                <!-- Anime Info Header Grid -->
                <div id="modal-info-view" class="grid grid-cols-1 md:grid-cols-3 gap-8">
                    <!-- Left: Poster -->
                    <div class="relative group rounded-xl overflow-hidden shadow-xl">
                        <img id="modal-poster" src="" alt="Poster" class="w-full h-80 md:h-[400px] object-cover">
                        <div id="modal-status-badge" class="absolute top-3 left-3 bg-emerald-500/90 text-white text-xs font-bold px-3 py-1 rounded-full shadow">
                            Онгоинг
                        </div>
                    </div>

                    <!-- Right: Info Details -->
                    <div class="md:col-span-2 flex flex-col justify-between">
                        <div>
                            <div class="flex items-center gap-3 mb-2">
                                <span id="modal-rating" class="bg-amber-500/20 border border-amber-500/40 text-amber-400 font-bold text-xs px-3 py-1 rounded-lg flex items-center gap-1">
                                    ⭐ 8.8
                                </span>
                                <span id="modal-episodes-count" class="bg-white/10 text-gray-300 font-semibold text-xs px-3 py-1 rounded-lg">
                                    📺 24 серии
                                </span>
                                <span id="modal-year" class="bg-white/10 text-gray-300 font-semibold text-xs px-3 py-1 rounded-lg">
                                    2026
                                </span>
                            </div>

                            <h2 id="modal-title" class="text-3xl sm:text-4xl font-display font-black text-white mb-1">
                                Название аниме
                            </h2>
                            <p id="modal-original-title" class="text-sm text-zenith-400 font-medium mb-4">
                                Original Title
                            </p>

                            <!-- Dubbing / Voiceover Info -->
                            <div class="flex items-center gap-2 mb-4 text-xs sm:text-sm text-gray-300 bg-white/5 p-3 rounded-xl border border-white/5">
                                <i class="fa-solid fa-microphone text-zenith-accent"></i>
                                <span>🎙️ Озвучка:</span>
                                <span id="modal-voiceover" class="font-bold text-white">AniLibria, Jam Club, HDRezka</span>
                            </div>

                            <!-- Description -->
                            <p id="modal-description" class="text-sm text-gray-300 leading-relaxed mb-6">
                                Описание аниме будет находиться здесь...
                            </p>

                            <!-- Genres Tags -->
                            <div id="modal-genres" class="flex flex-wrap gap-2 mb-8">
                                <!-- Dynamic genre tags -->
                            </div>
                        </div>

                        <!-- Action Buttons -->
                        <div class="flex flex-col sm:flex-row items-center gap-4 pt-4 border-t border-white/10">
                            <button onclick="startWatching()" class="w-full sm:w-auto btn-gradient text-white font-bold px-8 py-3.5 rounded-xl shadow-neon-violet hover:scale-105 transition-all flex items-center justify-center gap-2">
                                <i class="fa-solid fa-circle-play text-lg"></i>
                                <span>▶ Смотреть</span>
                            </button>

                            <button id="modal-fav-btn" onclick="toggleFavoriteModal()" class="w-full sm:w-auto glass-card hover:bg-white/10 text-white font-semibold px-6 py-3.5 rounded-xl transition-all flex items-center justify-center gap-2">
                                <i id="modal-fav-icon" class="fa-regular fa-heart text-zenith-accent"></i>
                                <span id="modal-fav-text">Добавить в избранное</span>
                            </button>
                        </div>
                    </div>
                </div>

                <!-- Embedded Custom Video Player View (Hidden by default) -->
                <div id="modal-player-view" class="hidden">
                    <div class="flex items-center justify-between mb-4">
                        <button onclick="backToInfo()" class="text-xs sm:text-sm text-gray-400 hover:text-white flex items-center gap-2">
                            <i class="fa-solid fa-arrow-left"></i> Назад к описанию
                        </button>
                        <h3 id="player-title" class="text-sm sm:text-base font-bold text-white">Серия 1</h3>
                    </div>

                    <!-- Custom HTML5 / Mock Video Player Container -->
                    <div class="relative bg-black rounded-2xl overflow-hidden aspect-video border border-white/10 shadow-2xl mb-6 group">
                        <video id="zenith-video" class="w-full h-full object-cover" poster="https://images.unsplash.com/photo-1578632767115-351597cf2477?q=80&w=1200&auto=format&fit=crop">
                            <source src="https://commondatastorage.googleapis.com/gtv-videos-bucket/sample/TearsOfSteel.mp4" type="video/mp4">
                        </video>
                        
                        <!-- Overlay Play Button -->
                        <div id="video-overlay" onclick="togglePlayVideo()" class="absolute inset-0 bg-black/40 flex items-center justify-center cursor-pointer transition-opacity">
                            <div class="w-16 h-16 sm:w-20 sm:h-20 rounded-full btn-gradient flex items-center justify-center text-white text-2xl shadow-neon-violet group-hover:scale-110 transition-transform">
                                <i id="overlay-play-icon" class="fa-solid fa-play ml-1"></i>
                            </div>
                        </div>
                    </div>

                    <!-- Episode Selector Grid -->
                    <div>
                        <h4 class="text-sm font-bold text-white mb-3 flex items-center gap-2">
                            <span>📺</span> Выбор серии:
                        </h4>
                        <div id="episodes-grid" class="flex flex-wrap gap-2 max-h-40 overflow-y-auto p-1">
                            <!-- Dynamic Episode Buttons -->
                        </div>
                    </div>
                </div>

            </div>
        </div>
    </div>

    <!-- Footer -->
    <footer class="glass-header border-t border-white/10 py-12 mt-20">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex flex-col md:flex-row items-center justify-between gap-6 pb-8 border-b border-white/5">
                
                <div class="text-center md:text-left">
                    <div class="flex items-center justify-center md:justify-start gap-2 mb-2">
                        <div class="w-8 h-8 rounded-lg btn-gradient flex items-center justify-center text-white font-black text-sm shadow-neon-indigo">
                            <i class="fa-solid fa-play text-xs"></i>
                        </div>
                        <span class="text-2xl font-display font-black tracking-widest text-gradient">
                            ᴢᴇɴɪᴛʜ
                        </span>
                    </div>
                    <p class="text-xs text-gray-400">Онлайн просмотр аниме • Аниме әлеміне қош келдің!</p>
                </div>

                <!-- Social Links -->
                <div class="flex items-center gap-4">
                    <a href="#" class="w-10 h-10 rounded-xl glass-card flex items-center justify-center text-gray-300 hover:text-indigo-400 hover:border-indigo-500/50 transition-all">
                        <i class="fa-brands fa-discord"></i>
                    </a>
                    <a href="#" class="w-10 h-10 rounded-xl glass-card flex items-center justify-center text-gray-300 hover:text-sky-400 hover:border-sky-500/50 transition-all">
                        <i class="fa-brands fa-telegram"></i>
                    </a>
                    <a href="#" class="w-10 h-10 rounded-xl glass-card flex items-center justify-center text-gray-300 hover:text-pink-400 hover:border-pink-500/50 transition-all">
                        <i class="fa-brands fa-instagram"></i>
                    </a>
                </div>
            </div>

            <div class="pt-6 flex flex-col sm:flex-row items-center justify-between text-xs text-gray-500 gap-4">
                <p>© 2026 ZENITH Anime. Барлық құқықтар қорғалған.</p>
                <p class="text-gray-600">Все видеоматериалы предоставлены исключительно для ознакомления.</p>
            </div>
        </div>
    </footer>

    <!-- Toast Notification -->
    <div id="toast" class="fixed bottom-6 right-6 z-50 transform translate-y-20 opacity-0 transition-all duration-300 glass-card border border-zenith-accent/50 px-5 py-3.5 rounded-xl shadow-neon-violet flex items-center gap-3">
        <i id="toast-icon" class="fa-solid fa-circle-check text-zenith-accent text-lg"></i>
        <span id="toast-message" class="text-sm font-semibold text-white">Добавлено в избранное!</span>
    </div>

    <!-- JavaScript Application Logic -->
    <script>
        // Mock Anime Database
        const ANIME_DATA = [
            {
                id: 1,
                title: "Поднятие уровня в одиночку",
                originalTitle: "Solo Leveling / Ore dake Level Up na Ken",
                rating: "9.1",
                episodes: 24,
                status: "Онгоинг",
                year: 2026,
                poster: "https://images.unsplash.com/photo-1534447677768-be436bb09401?q=80&w=800&auto=format&fit=crop",
                voiceover: "AniLibria, Jam Club, HDRezka",
                genres: ["Экшен", "Фэнтези", "Приключения"],
                description: "В мире, где из неизвестно откуда взявшихся врат начали появляться монстры, а обычные люди обрели сверхспособности и стали называться Охотниками, слабый охотник E-ранга Сон Джин-у сталкивается с опасностью.",
                latestEpisode: "Серия 12 🟢",
                updatedAgo: "10 минут назад"
            },
            {
                id: 2,
                title: "Клинок, рассекающий демонов",
                originalTitle: "Demon Slayer / Kimetsu no Yaiba",
                rating: "8.9",
                episodes: 26,
                status: "Завершен",
                year: 2024,
                poster: "https://images.unsplash.com/photo-1578632767115-351597cf2477?q=80&w=800&auto=format&fit=crop",
                voiceover: "Studio Band, AniLibria",
                genres: ["Экшен", "Фэнтези", "Драма"],
                description: "Танджиро Камадо — добрый и умный мальчик, который живет со своей семьей в горах. Все меняется, когда его семья подвергается нападению демонов.",
                latestEpisode: "Серия 26 🟢",
                updatedAgo: "1 час назад"
            },
            {
                id: 3,
                title: "Магическая битва",
                originalTitle: "Jujutsu Kaisen",
                rating: "8.8",
                episodes: 24,
                status: "Онгоинг",
                year: 2025,
                poster: "https://images.unsplash.com/photo-1607604276583-eef5d076aa5f?q=80&w=800&auto=format&fit=crop",
                voiceover: "AniLibria, Deep, HDRezka",
                genres: ["Экшен", "Школа", "Фэнтези"],
                description: "Старшеклассник Юдзи Итадори обладает незаурядной физической силой, но предпочитает проводить время в оккультном клубе.",
                latestEpisode: "Серия 18 🟢",
                updatedAgo: "2 часа назад"
            },
            {
                id: 4,
                title: "Провожающая в последний путь Фрирен",
                originalTitle: "Sousou no Frieren",
                rating: "9.3",
                episodes: 28,
                status: "Завершен",
                year: 2024,
                poster: "https://images.unsplash.com/photo-1518709268805-4e9042af9f23?q=80&w=800&auto=format&fit=crop",
                voiceover: "AniLibria, Subtitles",
                genres: ["Фэнтези", "Приключения", "Драма"],
                description: "История эльфийки Фрирен, волшебницы из отряда героев, победвших Повелителя демонов. После 10-летнего путешествия отряд распадается.",
                latestEpisode: "Серия 28 🟢",
                updatedAgo: "Вчера"
            },
            {
                id: 5,
                title: "Человек-бензопила",
                originalTitle: "Chainsaw Man",
                rating: "8.7",
                episodes: 12,
                status: "Завершен",
                year: 2023,
                poster: "https://images.unsplash.com/photo-1563089145-599997674d42?q=80&w=800&auto=format&fit=crop",
                voiceover: "Jam Club, HDRezka",
                genres: ["Экшен", "Фантастика", "Комедия"],
                description: "Дэндзи — молодой парень, вынужденный расплачиваться с долгами своего покойного отца, охотясь на демонов вместе с Почитой.",
                latestEpisode: "Серия 12 🟢",
                updatedAgo: "3 дня назад"
            },
            {
                id: 6,
                title: "Атака титанов",
                originalTitle: "Attack on Titan / Shingeki no Kyojin",
                rating: "9.0",
                episodes: 87,
                status: "Завершен",
                year: 2023,
                poster: "https://images.unsplash.com/photo-1541701494587-cb58502866ab?q=80&w=800&auto=format&fit=crop",
                voiceover: "Studio Band, AniLibria",
                genres: ["Экшен", "Драма", "Фантастика"],
                description: "Уже 100 лет человечество живет за тремя огромными стенами, защищающими людей от гигантских людоедов — титанов.",
                latestEpisode: "Серия 87 🟢",
                updatedAgo: "Неделю назад"
            }
        ];

        const GENRES_LIST = ["Все", "Экшен", "Приключения", "Комедия", "Фэнтези", "Романтика", "Драма", "Школа", "Фантастика"];

        // State Management
        let currentSelectedAnime = null;
        let activeGenreFilter = "Все";
        let favorites = JSON.parse(localStorage.getItem('zenith_favorites')) || [];

        // App Initialization
        window.onload = function() {
            renderPopular();
            renderUpdates();
            renderGenresPills();
            updateFavoritesCounter();
        };

        // Render Popular Anime
        function renderPopular() {
            const container = document.getElementById('popular-container');
            container.innerHTML = ANIME_DATA.map(anime => `
                <div onclick="openAnimeModal(${anime.id})" class="glass-card rounded-2xl overflow-hidden shrink-0 w-48 sm:w-56 cursor-pointer group">
                    <div class="relative h-64 sm:h-72 overflow-hidden">
                        <img src="${anime.poster}" alt="${anime.title}" class="w-full h-full object-cover group-hover:scale-110 transition-transform duration-500">
                        <div class="absolute top-3 right-3 bg-black/60 backdrop-blur-md text-amber-400 text-xs font-extrabold px-2.5 py-1 rounded-lg border border-amber-500/30">
                            ⭐ ${anime.rating}
                        </div>
                        <div class="absolute bottom-3 left-3 bg-black/60 backdrop-blur-md text-gray-200 text-xs font-semibold px-2.5 py-1 rounded-lg border border-white/10">
                            Серий: ${anime.episodes}
                        </div>
                    </div>
                    <div class="p-4">
                        <h3 class="font-bold text-white text-sm sm:text-base line-clamp-1 group-hover:text-zenith-400 transition-colors">${anime.title}</h3>
                        <p class="text-xs text-gray-400 mt-1">${anime.genres[0]} • ${anime.year}</p>
                    </div>
                </div>
            `).join('');
        }

        // Render Latest Updates
        function renderUpdates() {
            const container = document.getElementById('updates-container');
            container.innerHTML = ANIME_DATA.slice(0, 6).map(anime => `
                <div onclick="openAnimeModal(${anime.id})" class="glass-card p-4 rounded-2xl flex gap-4 cursor-pointer group">
                    <img src="${anime.poster}" alt="${anime.title}" class="w-20 h-28 object-cover rounded-xl shrink-0 group-hover:scale-105 transition-transform">
                    <div class="flex flex-col justify-between py-1 flex-grow">
                        <div>
                            <div class="flex items-center justify-between mb-1">
                                <span class="text-xs font-bold text-emerald-400 flex items-center gap-1">
                                    ${anime.latestEpisode}
                                </span>
                                <span class="text-[10px] text-gray-500">${anime.updatedAgo}</span>
                            </div>
                            <h3 class="font-bold text-white text-sm group-hover:text-zenith-400 transition-colors line-clamp-1">${anime.title}</h3>
                            <p class="text-xs text-gray-400 line-clamp-1 mt-0.5">🎙️ ${anime.voiceover}</p>
                        </div>
                        <div class="flex items-center gap-2 text-[10px] text-gray-400">
                            <span class="bg-white/5 px-2 py-0.5 rounded">${anime.genres[0]}</span>
                            <span class="text-amber-400 font-bold">⭐ ${anime.rating}</span>
                        </div>
                    </div>
                </div>
            `).join('');
        }

        // Render Genre Pills
        function renderGenresPills() {
            const container = document.getElementById('genres-pills');
            container.innerHTML = GENRES_LIST.map(genre => `
                <button onclick="filterByGenre('${genre}')" class="genre-pill px-5 py-2.5 rounded-xl text-xs sm:text-sm font-semibold transition-all ${genre === activeGenreFilter ? 'btn-gradient text-white shadow-neon-indigo' : 'glass-card text-gray-300 hover:text-white'}">
                    ${genre}
                </button>
            `).join('');
        }

        // Filter by Genre Action
        function filterByGenre(genre) {
            activeGenreFilter = genre;
            renderGenresPills();

            const title = document.getElementById('catalog-title');
            const subtitle = document.getElementById('catalog-subtitle');
            
            title.innerText = genre === 'Все' ? 'Все Аниме' : `Жанр: ${genre}`;
            subtitle.innerText = `Список аниме в категории ${genre}`;

            const filtered = genre === 'Все' ? ANIME_DATA : ANIME_DATA.filter(a => a.genres.includes(genre));
            renderCatalogGrid(filtered);
            switchMainTab('catalog');
        }

        // Render Catalog Grid
        function renderCatalogGrid(list) {
            const container = document.getElementById('catalog-grid');
            if (list.length === 0) {
                container.innerHTML = `<p class="col-span-full text-center py-10 text-gray-400">Ничего не найдено</p>`;
                return;
            }

            container.innerHTML = list.map(anime => `
                <div onclick="openAnimeModal(${anime.id})" class="glass-card rounded-2xl overflow-hidden cursor-pointer group">
                    <div class="relative h-60 sm:h-64 overflow-hidden">
                        <img src="${anime.poster}" alt="${anime.title}" class="w-full h-full object-cover group-hover:scale-110 transition-transform duration-500">
                        <div class="absolute top-2 right-2 bg-black/60 backdrop-blur-md text-amber-400 text-xs font-extrabold px-2 py-0.5 rounded">
                            ⭐ ${anime.rating}
                        </div>
                    </div>
                    <div class="p-3">
                        <h3 class="font-bold text-white text-xs sm:text-sm line-clamp-1 group-hover:text-zenith-400">${anime.title}</h3>
                        <p class="text-[10px] text-gray-400 mt-1">${anime.episodes} серий • ${anime.year}</p>
                    </div>
                </div>
            `).join('');
        }

        // Search Dynamic Filtering
        function handleSearch(query) {
            const clearBtn = document.getElementById('clear-search');
            if (query.trim().length > 0) {
                clearBtn.classList.remove('hidden');
                const filtered = ANIME_DATA.filter(a => 
                    a.title.toLowerCase().includes(query.toLowerCase()) || 
                    a.originalTitle.toLowerCase().includes(query.toLowerCase())
                );
                document.getElementById('catalog-title').innerText = `Поиск: "${query}"`;
                document.getElementById('catalog-subtitle').innerText = `Найдено результатов: ${filtered.length}`;
                renderCatalogGrid(filtered);
                switchMainTab('catalog');
            } else {
                clearBtn.classList.add('hidden');
                switchMainTab('home');
            }
        }

        function clearSearch() {
            document.getElementById('search-input').value = '';
            document.getElementById('clear-search').classList.add('hidden');
            switchMainTab('home');
        }

        function filterOngoing() {
            const ongoingList = ANIME_DATA.filter(a => a.status === 'Онгоинг');
            document.getElementById('catalog-title').innerText = "Онгоинги";
            document.getElementById('catalog-subtitle').innerText = "Аниме, выходящие в эфир прямо сейчас";
            renderCatalogGrid(ongoingList);
            switchMainTab('catalog');
        }

        // Tab Switching Engine
        function switchMainTab(tab) {
            const views = ['home', 'catalog', 'favorites'];
            views.forEach(v => {
                const elem = document.getElementById(`view-${v}`);
                if (v === tab) {
                    elem.classList.remove('hidden');
                } else {
                    elem.classList.add('hidden');
                }
            });

            // Update Nav active styles
            document.querySelectorAll('.nav-btn').forEach(btn => {
                btn.className = "nav-btn px-3.5 py-2 rounded-xl text-sm font-semibold text-gray-300 hover:text-white hover:bg-white/5 transition-all";
            });

            if (tab === 'home') document.getElementById('nav-home').className = "nav-btn px-3.5 py-2 rounded-xl text-sm font-semibold text-white bg-white/10 transition-all";
            if (tab === 'anime') {
                filterByGenre('Все');
                document.getElementById('nav-anime').className = "nav-btn px-3.5 py-2 rounded-xl text-sm font-semibold text-white bg-white/10 transition-all";
            }
            if (tab === 'favorites') {
                renderFavorites();
                document.getElementById('nav-favorites').className = "nav-btn px-3.5 py-2 rounded-xl text-sm font-semibold text-white bg-white/10 transition-all";
            }

            window.scrollTo({ top: 0, behavior: 'smooth' });
        }

        // Favorites System (LocalStorage)
        function toggleFavorite(id) {
            const index = favorites.indexOf(id);
            if (index === -1) {
                favorites.push(id);
                showToast("Добавлено в избранное!");
            } else {
                favorites.splice(index, 1);
                showToast("Удалено из избранного!");
            }
            localStorage.setItem('zenith_favorites', JSON.stringify(favorites));
            updateFavoritesCounter();
            updateModalFavButton();
            if (!document.getElementById('view-favorites').classList.contains('hidden')) {
                renderFavorites();
            }
        }

        function toggleFavoriteModal() {
            if (currentSelectedAnime) {
                toggleFavorite(currentSelectedAnime.id);
            }
        }

        function updateFavoritesCounter() {
            const count = favorites.length;
            document.getElementById('fav-counter').innerText = count;
            document.getElementById('fav-counter-mobile').innerText = count;
        }

        function renderFavorites() {
            const favGrid = document.getElementById('favorites-grid');
            const emptyState = document.getElementById('favorites-empty');

            if (favorites.length === 0) {
                favGrid.innerHTML = '';
                emptyState.classList.remove('hidden');
                return;
            }

            emptyState.classList.add('hidden');
            const favAnimeList = ANIME_DATA.filter(a => favorites.includes(a.id));

            favGrid.innerHTML = favAnimeList.map(anime => `
                <div onclick="openAnimeModal(${anime.id})" class="glass-card rounded-2xl overflow-hidden cursor-pointer group">
                    <div class="relative h-60 sm:h-64 overflow-hidden">
                        <img src="${anime.poster}" alt="${anime.title}" class="w-full h-full object-cover group-hover:scale-110 transition-transform duration-500">
                        <div class="absolute top-2 right-2 bg-black/60 backdrop-blur-md text-amber-400 text-xs font-extrabold px-2 py-0.5 rounded">
                            ⭐ ${anime.rating}
                        </div>
                    </div>
                    <div class="p-3">
                        <h3 class="font-bold text-white text-xs sm:text-sm line-clamp-1 group-hover:text-zenith-400">${anime.title}</h3>
                        <p class="text-[10px] text-gray-400 mt-1">${anime.episodes} серий • ${anime.year}</p>
                    </div>
                </div>
            `).join('');
        }

        // Modal Anime Player Functions
        function openAnimeModal(id) {
            const anime = ANIME_DATA.find(a => a.id === id);
            if (!anime) return;

            currentSelectedAnime = anime;

            // Set info details
            document.getElementById('modal-poster').src = anime.poster;
            document.getElementById('modal-title').innerText = anime.title;
            document.getElementById('modal-original-title').innerText = anime.originalTitle;
            document.getElementById('modal-rating').innerText = `⭐ ${anime.rating}`;
            document.getElementById('modal-episodes-count').innerText = `📺 ${anime.episodes} серии`;
            document.getElementById('modal-year').innerText = anime.year;
            document.getElementById('modal-voiceover').innerText = anime.voiceover;
            document.getElementById('modal-description').innerText = anime.description;
            document.getElementById('modal-status-badge').innerText = anime.status;

            // Genres tags
            document.getElementById('modal-genres').innerHTML = anime.genres.map(g => `
                <span class="bg-white/10 text-xs font-semibold px-3 py-1 rounded-lg text-gray-200">${g}</span>
            `).join('');

            updateModalFavButton();
            backToInfo();

            // Render Episodes grid
            renderEpisodesGrid(anime.episodes);

            // Open Modal
            const modal = document.getElementById('anime-modal');
            modal.classList.remove('hidden');
            setTimeout(() => {
                modal.classList.remove('opacity-0');
            }, 10);
        }

        function closeAnimeModal() {
            const modal = document.getElementById('anime-modal');
            modal.classList.add('opacity-0');
            
            // Pause video if playing
            const video = document.getElementById('zenith-video');
            video.pause();

            setTimeout(() => {
                modal.classList.add('hidden');
            }, 300);
        }

        function updateModalFavButton() {
            if (!currentSelectedAnime) return;
            const isFav = favorites.includes(currentSelectedAnime.id);
            const icon = document.getElementById('modal-fav-icon');
            const text = document.getElementById('modal-fav-text');

            if (isFav) {
                icon.className = "fa-solid fa-heart text-zenith-accent";
                text.innerText = "В избранном";
            } else {
                icon.className = "fa-regular fa-heart text-zenith-accent";
                text.innerText = "Добавить в избранное";
            }
        }

        function renderEpisodesGrid(count) {
            const grid = document.getElementById('episodes-grid');
            let html = '';
            for (let i = 1; i <= count; i++) {
                html += `
                    <button onclick="selectEpisode(${i})" id="ep-btn-${i}" class="ep-btn px-4 py-2 rounded-xl text-xs font-bold transition-all ${i === 1 ? 'btn-gradient text-white shadow-neon-violet' : 'glass-card text-gray-300 hover:text-white'}">
                        Серия ${i}
                    </button>
                `;
            }
            grid.innerHTML = html;
        }

        function selectEpisode(num) {
            document.querySelectorAll('.ep-btn').forEach(btn => {
                btn.className = "ep-btn px-4 py-2 rounded-xl text-xs font-bold glass-card text-gray-300 hover:text-white transition-all";
            });
            document.getElementById(`ep-btn-${num}`).className = "ep-btn px-4 py-2 rounded-xl text-xs font-bold btn-gradient text-white shadow-neon-violet transition-all";
            document.getElementById('player-title').innerText = `Серия ${num}`;

            // Reset video play status
            const video = document.getElementById('zenith-video');
            video.currentTime = 0;
            video.play();
            document.getElementById('video-overlay').classList.add('opacity-0', 'pointer-events-none');
        }

        function startWatching() {
            document.getElementById('modal-info-view').classList.add('hidden');
            document.getElementById('modal-player-view').classList.remove('hidden');
        }

        function backToInfo() {
            document.getElementById('modal-player-view').classList.add('hidden');
            document.getElementById('modal-info-view').classList.remove('hidden');
        }

        function togglePlayVideo() {
            const video = document.getElementById('zenith-video');
            const overlay = document.getElementById('video-overlay');
            if (video.paused) {
                video.play();
                overlay.classList.add('opacity-0', 'pointer-events-none');
            } else {
                video.pause();
                overlay.classList.remove('opacity-0', 'pointer-events-none');
            }
        }

        // Horizontal Scroll Helper
        function scrollGrid(id, offset) {
            document.getElementById(id).scrollBy({ left: offset, behavior: 'smooth' });
        }

        // Toast Notification Helper
        function showToast(message) {
            const toast = document.getElementById('toast');
    
