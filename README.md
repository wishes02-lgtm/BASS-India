<!DOCTYPE html>
<html lang="en" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>BASS India | Bhilang Aadivaasee Saamaajik Samiti</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        brand: {
                            navy: '#0B192C',     /* Deep navy from logo text/shadows */
                            teal: '#1E3E62',     /* Rich dark teal */
                            aqua: '#008DDA',     /* Vibrant river blue from logo */
                            sky: '#41C9E2',      /* Soft bright aqua */
                            green: '#2E7D32',    /* Vibrant leaf green */
                            lime: '#81C784',     /* Light leaf green */
                            gold: '#FFB300',     /* Warm sunrise gold from birds/women */
                        }
                    }
                }
            }
        }
    </script>
    <!-- Lucide Icons -->
    <script src="https://unpkg.com/lucide@latest"></script>
    <!-- Google Fonts: Plus Jakarta Sans & Outfit (Gen Z / Modern Startup aesthetic) -->
    <link href="https://fonts.googleapis.com/css2?family=Outfit:wght@400;500;600;700;800&family=Plus+Jakarta+Sans:wght@400;500;600;700&display=swap" rel="stylesheet">
    <style>
        body { font-family: 'Plus Jakarta Sans', sans-serif; }
        h1, h2, h3, h4, .font-heading { font-family: 'Outfit', sans-serif; }
        .slide { display: none; }
        .slide.active { display: block; animation: zoomFade 1.2s cubic-bezier(0.16, 1, 0.3, 1) forwards; }
        @keyframes zoomFade {
            from { opacity: 0; transform: scale(1.04); }
            to { opacity: 1; transform: scale(1); }
        }
        /* Glassmorphism effects */
        .glass-card {
            background: rgba(255, 255, 255, 0.85);
            backdrop-filter: blur(16px);
            border: 1px solid rgba(255, 255, 255, 0.4);
        }
        .glass-dark {
            background: rgba(11, 25, 44, 0.85);
            backdrop-filter: blur(16px);
            border: 1px solid rgba(65, 201, 226, 0.15);
        }
    </style>
</head>
<body class="bg-slate-50 text-slate-800 antialiased selection:bg-brand-aqua selection:text-white">

    <!-- Top Announcement Bar (Logo color matched) -->
    <div class="bg-brand-navy text-slate-200 text-xs py-2 px-4 sm:px-8 flex flex-col sm:flex-row justify-between items-center gap-2 border-b border-brand-teal">
        <div class="flex items-center gap-4">
            <span class="flex items-center gap-1.5"><i data-lucide="map-pin" class="w-3.5 h-3.5 text-brand-gold"></i> Jhabua, Madhya Pradesh | Pan-India Mandate</span>
            <span class="hidden md:inline-flex items-center gap-1.5"><i data-lucide="shield-check" class="w-3.5 h-3.5 text-brand-sky"></i> 80G, 12A & CSR-1 Certified</span>
        </div>
        <div class="flex items-center gap-4">
            <a href="#contact" class="hover:text-brand-sky transition font-medium">CSR Partnerships</a>
            <span>|</span>
            <a href="#donate" class="hover:text-brand-gold transition font-bold text-brand-gold flex items-center gap-1"><i data-lucide="heart" class="w-3 h-3 fill-current"></i> Quick Donate</a>
            <span>|</span>
            <button onclick="toggleLanguage()" id="langBtn" class="bg-brand-teal hover:bg-brand-aqua text-white px-2.5 py-0.5 rounded text-xs transition font-semibold">हिंदी / English</button>
        </div>
    </div>

    <!-- Sticky Navigation Header -->
    <header class="sticky top-0 z-50 bg-white/90 backdrop-blur-md shadow-sm border-b border-slate-200 transition-all">
        <div class="max-w-7xl mx-auto px-4 sm:px-8 py-3.5 flex items-center justify-between">
            
            <!-- Brand Logo Integrated from Source -->
            <a href="#home" class="flex items-center gap-3.5 group">
                <div class="w-12 h-12 rounded-full overflow-hidden border-2 border-brand-aqua shadow-md bg-white p-0.5 flex items-center justify-center group-hover:scale-105 transition">
                    <img src="BASS India Logo.jpeg" alt="BASS India Logo" class="w-full h-full object-cover rounded-full">
                </div>
                <div>
                    <span class="text-xl font-extrabold tracking-tight text-brand-navy font-heading leading-none block">BASS India</span>
                    <span class="text-[9px] text-slate-500 font-semibold tracking-wider uppercase block mt-0.5">Bhilang Aadivaasee Samiti</span>
                </div>
            </a>

            <!-- Desktop Menu -->
            <nav class="hidden lg:flex items-center gap-7 text-sm font-semibold text-slate-700">
                <a href="#home" class="text-brand-aqua transition hover:text-brand-teal">Home</a>
                <a href="#about" class="transition hover:text-brand-aqua">About Us</a>
                <a href="#programs" class="transition hover:text-brand-aqua">Programs</a>
                <a href="#impact" class="transition hover:text-brand-aqua">Impact</a>
                <a href="#stories" class="transition hover:text-brand-aqua">Stories</a>
                <a href="#resources" class="transition hover:text-brand-aqua">Resources</a>
                <a href="#contact" class="transition hover:text-brand-aqua">Contact</a>
            </nav>

            <!-- Gen-Z / Modern CTAs -->
            <div class="hidden sm:flex items-center gap-3">
                <a href="#get-involved" class="text-xs font-bold uppercase tracking-wider text-brand-navy bg-slate-100 hover:bg-slate-200 px-4 py-2.5 rounded-xl transition">Join Movement</a>
                <a href="#donate" class="text-xs font-bold uppercase tracking-wider text-brand-navy bg-brand-gold hover:bg-amber-400 px-4 py-2.5 rounded-xl shadow-md transition flex items-center gap-1.5 transform hover:-translate-y-0.5">
                    <i data-lucide="sparkles" class="w-3.5 h-3.5"></i> Donate 80G
                </a>
            </div>

            <!-- Mobile Menu Toggle -->
            <button onclick="toggleMobileMenu()" class="lg:hidden p-2 text-slate-700 hover:text-brand-navy focus:outline-none">
                <i data-lucide="menu" class="w-6 h-6"></i>
            </button>
        </div>

        <!-- Mobile Dropdown Menu -->
        <div id="mobileMenu" class="hidden lg:hidden bg-white border-b border-slate-200 px-6 py-5 space-y-3 shadow-xl">
            <a href="#home" class="block text-slate-700 hover:text-brand-aqua font-semibold py-1">Home</a>
            <a href="#about" class="block text-slate-700 hover:text-brand-aqua font-semibold py-1">About Us</a>
            <a href="#programs" class="block text-slate-700 hover:text-brand-aqua font-semibold py-1">Programs</a>
            <a href="#impact" class="block text-slate-700 hover:text-brand-aqua font-semibold py-1">Impact</a>
            <a href="#stories" class="block text-slate-700 hover:text-brand-aqua font-semibold py-1">Stories</a>
            <a href="#resources" class="block text-slate-700 hover:text-brand-aqua font-semibold py-1">Resources</a>
            <a href="#contact" class="block text-slate-700 hover:text-brand-aqua font-semibold py-1">Contact</a>
            <div class="pt-4 flex flex-col gap-2.5 border-t border-slate-100">
                <a href="#get-involved" class="text-center font-bold text-xs uppercase tracking-wider text-brand-navy bg-slate-100 py-3 rounded-xl">Join Movement</a>
                <a href="#donate" class="text-center font-bold text-xs uppercase tracking-wider text-brand-navy bg-brand-gold py-3 rounded-xl shadow">Donate 80G</a>
            </div>
        </div>
    </header>

    <!-- Modern Hero Slideshow Section -->
    <section id="home" class="relative bg-brand-navy text-white overflow-hidden h-[620px] lg:h-[700px] flex items-center">
        <!-- Slideshow Backgrounds with authentic tribal area representation -->
        <div class="absolute inset-0 z-0">
            <!-- Slide 1: Afforestation & Green Hills -->
            <div class="slide active absolute inset-0 bg-cover bg-center transition-opacity duration-1000" style="background-image: url('https://images.unsplash.com/photo-1542601906990-b4d3fb778b09?auto=format&fit=crop&q=80&w=1600');">
                <div class="absolute inset-0 bg-gradient-to-r from-brand-navy via-brand-teal/80 to-transparent"></div>
            </div>
            <!-- Slide 2: Tribal Women Empowerment & SHG Collectives -->
            <div class="slide absolute inset-0 bg-cover bg-center transition-opacity duration-1000" style="background-image: url('https://images.unsplash.com/photo-1573497019940-1c28c88b4f3e?auto=format&fit=crop&q=80&w=1600');">
                <div class="absolute inset-0 bg-gradient-to-r from-brand-navy via-brand-teal/80 to-transparent"></div>
            </div>
            <!-- Slide 3: Sustainable Agriculture & Watershed -->
            <div class="slide absolute inset-0 bg-cover bg-center transition-opacity duration-1000" style="background-image: url('https://images.unsplash.com/photo-1500937386664-56d1dfef3854?auto=format&fit=crop&q=80&w=1600');">
                <div class="absolute inset-0 bg-gradient-to-r from-brand-navy via-brand-teal/80 to-transparent"></div>
            </div>
        </div>

        <div class="relative z-10 max-w-7xl mx-auto px-4 sm:px-8 w-full grid grid-cols-1 lg:grid-cols-12 gap-12 items-center">
            <div class="lg:col-span-8 space-y-6">
                <div class="inline-flex items-center gap-2 bg-brand-teal/80 border border-brand-aqua/40 text-brand-gold px-4 py-2 rounded-full text-xs font-bold tracking-wide uppercase shadow-lg">
                    <i data-lucide="sparkles" class="w-3.5 h-3.5"></i> Empowering communities for a sustainable future
                </div>
                <h1 id="heroTitle" class="text-4xl sm:text-6xl lg:text-7xl font-extrabold tracking-tight font-heading leading-[1.08]">
                    Reimagining Tribal Futures, <span class="text-brand-sky">Restoring Nature.</span>
                </h1>
                <p id="heroSubtitle" class="text-lg text-slate-200 max-w-2xl leading-relaxed font-normal">
                    Bhilang Aadivaasee Saamaajik Samiti (BASS India) combines indigenous wisdom with modern tech and climate action. Fueling grassroots women entrepreneurship, watershed restoration, and afforestation across Jhabua, Dhar, Alirajpur, and Banswara.
                </p>
                <div class="flex flex-wrap gap-4 pt-4">
                    <a href="#programs" class="bg-brand-gold hover:bg-amber-400 text-brand-navy font-extrabold px-8 py-4 rounded-2xl shadow-xl transition flex items-center gap-2 transform hover:-translate-y-0.5">
                        Explore Initiatives <i data-lucide="arrow-right" class="w-4 h-4"></i>
                    </a>
                    <a href="#get-involved" class="bg-white/10 hover:bg-white/20 border border-white/25 text-white font-bold px-8 py-4 rounded-2xl backdrop-blur-md transition">
                        Join Volunteer Network
                    </a>
                </div>
            </div>
        </div>

        <!-- Modern Slide Indicators -->
        <div class="absolute bottom-8 right-8 z-20 flex items-center gap-3 bg-brand-navy/80 backdrop-blur-md px-5 py-2.5 rounded-full border border-brand-aqua/30">
            <button onclick="prevSlide()" class="text-white hover:text-brand-sky p-1 transition"><i data-lucide="chevron-left" class="w-5 h-5"></i></button>
            <div class="flex gap-2">
                <span class="dot w-2.5 h-2.5 rounded-full bg-brand-gold cursor-pointer transition" onclick="currentSlide(0)"></span>
                <span class="dot w-2.5 h-2.5 rounded-full bg-slate-500 cursor-pointer transition" onclick="currentSlide(1)"></span>
                <span class="dot w-2.5 h-2.5 rounded-full bg-slate-500 cursor-pointer transition" onclick="currentSlide(2)"></span>
            </div>
            <button onclick="nextSlide()" class="text-white hover:text-brand-sky p-1 transition"><i data-lucide="chevron-right" class="w-5 h-5"></i></button>
        </div>
    </section>

    <!-- About Us & Vision/Mission/Story Section -->
    <section id="about" class="py-24 bg-white relative overflow-hidden">
        <div class="max-w-7xl mx-auto px-4 sm:px-8">
            <div class="text-center max-w-3xl mx-auto mb-16 space-y-3">
                <span class="text-xs font-bold uppercase tracking-widest text-brand-aqua">About BASS India</span>
                <h2 class="text-3xl sm:text-5xl font-extrabold tracking-tight text-brand-navy font-heading">Rooted in Jhabua, Growing for India</h2>
                <div class="w-24 h-1.5 bg-brand-gold mx-auto rounded-full"></div>
            </div>

            <div class="grid grid-cols-1 lg:grid-cols-12 gap-12 items-center mb-20">
                <div class="lg:col-span-6 space-y-6">
                    <h3 class="text-2xl font-bold text-brand-teal font-heading">Our Story: Empowering Communities for a Sustainable Future</h3>
                    <p class="text-slate-600 leading-relaxed text-base">
                        The journey of <strong>Bhilang Aadivaasee Saamaajik Samiti (BASS India)</strong> began in the culturally vibrant, rugged tribal terrain of Jhabua, Madhya Pradesh. We exist to convert traditional vulnerabilities into dynamic ecosystems of self-reliance, green growth, and economic dignity.
                    </p>
                    <p class="text-slate-600 leading-relaxed text-base">
                        With operational anchors across <strong>Jhabua, Dhar, and Alirajpur</strong> (MP) and <strong>Banswara</strong> (Rajasthan)—and a nationwide permit—we spearhead aggressive <strong>Climate Change Initiatives and Afforestation Projects</strong>. We believe ecological revival and women-led entrepreneurship are two sides of the same coin.
                    </p>
                </div>
                <div class="lg:col-span-6 relative">
                    <div class="absolute -inset-3 bg-gradient-to-tr from-brand-aqua/20 to-brand-gold/20 rounded-3xl transform rotate-1"></div>
                    <img src="https://images.unsplash.com/photo-1593113598332-cd288d649433?auto=format&fit=crop&q=80&w=800" alt="Tribal community field work" class="relative rounded-2xl shadow-2xl w-full h-[400px] object-cover border-4 border-white">
                </div>
            </div>

            <!-- Vision & Mission Grid -->
            <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
                <div class="bg-slate-50 border border-slate-200/80 p-8 sm:p-10 rounded-3xl shadow-sm hover:shadow-xl transition group">
                    <div class="w-14 h-14 bg-brand-navy text-brand-gold rounded-2xl flex items-center justify-center mb-6 shadow-md group-hover:scale-110 transition">
                        <i data-lucide="eye" class="w-7 h-7"></i>
                    </div>
                    <h3 class="text-2xl font-bold text-brand-navy mb-4 font-heading">Our Vision</h3>
                    <p class="text-slate-700 leading-relaxed italic text-base">
                        "To build an equitable, climate-resilient, and self-reliant society where tribal and marginalized communities thrive in harmony with a rejuvenated environment, empowered by sustainable livelihoods, green growth, quality education, and inclusive governance."
                    </p>
                </div>

                <div class="bg-brand-teal text-white p-8 sm:p-10 rounded-3xl shadow-xl relative overflow-hidden group">
                    <div class="absolute -right-10 -bottom-10 opacity-10">
                        <i data-lucide="target" class="w-64 h-64 text-brand-sky"></i>
                    </div>
                    <div class="relative z-10">
                        <div class="w-14 h-14 bg-brand-gold text-brand-navy rounded-2xl flex items-center justify-center mb-6 shadow-md group-hover:scale-110 transition">
                            <i data-lucide="target" class="w-7 h-7"></i>
                        </div>
                        <h3 class="text-2xl font-bold text-white mb-4 font-heading">Our Mission</h3>
                        <ul class="space-y-3 text-slate-100 text-sm">
                            <li class="flex items-start gap-2.5">
                                <i data-lucide="check-circle-2" class="w-4 h-4 text-brand-gold shrink-0 mt-1"></i>
                                <span>Spearhead large-scale <strong>Climate Change Initiatives & Afforestation Projects</strong> to restore local ecology.</span>
                            </li>
                            <li class="flex items-start gap-2.5">
                                <i data-lucide="check-circle-2" class="w-4 h-4 text-brand-gold shrink-0 mt-1"></i>
                                <span>Foster <strong>Women Empowerment</strong> through Self-Help Groups (SHGs) and Farmer Producer Organizations (FPOs).</span>
                            </li>
                            <li class="flex items-start gap-2.5">
                                <i data-lucide="check-circle-2" class="w-4 h-4 text-brand-gold shrink-0 mt-1"></i>
                                <span>Drive ecosystem health via <strong>Integrated Watershed Management</strong> and soil conservation.</span>
                            </li>
                        </ul>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Core Thematic Areas (Logo Color Coded Cards) -->
    <section id="programs" class="py-24 bg-slate-100">
        <div class="max-w-7xl mx-auto px-4 sm:px-8">
            <div class="text-center max-w-3xl mx-auto mb-16 space-y-3">
                <span class="text-xs font-bold uppercase tracking-widest text-brand-aqua">What We Do</span>
                <h2 class="text-3xl sm:text-5xl font-extrabold tracking-tight text-brand-navy font-heading">Our Core Thematic Pillars</h2>
                <div class="w-24 h-1.5 bg-brand-gold mx-auto rounded-full"></div>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
                <!-- Program 1: Climate & Afforestation -->
                <div class="bg-white rounded-3xl overflow-hidden shadow-sm hover:shadow-2xl transition border border-slate-200 flex flex-col justify-between group">
                    <div>
                        <div class="h-52 overflow-hidden relative">
                            <img src="https://images.unsplash.com/photo-1511497584788-8767611925b4?auto=format&fit=crop&q=80&w=600" alt="Afforestation" class="w-full h-full object-cover group-hover:scale-105 transition duration-700">
                            <span class="absolute top-4 left-4 bg-brand-navy/90 text-brand-gold text-xs font-bold px-3.5 py-1 rounded-full uppercase tracking-wider shadow">Climate Action</span>
                        </div>
                        <div class="p-7 space-y-3">
                            <h3 class="text-xl font-bold text-brand-navy font-heading">Climate Change & Afforestation</h3>
                            <p class="text-slate-600 text-sm leading-relaxed">
                                Massive tree plantation drives, native flora restoration, soil carbon capture, and community-led green resilience across tribal hills.
                            </p>
                        </div>
                    </div>
                    <div class="px-7 pb-7 pt-2">
                        <a href="#contact" class="text-brand-aqua font-bold text-xs uppercase tracking-wider inline-flex items-center gap-1.5 hover:text-brand-navy transition">
                            Explore Project <i data-lucide="arrow-right" class="w-3.5 h-3.5"></i>
                        </a>
                    </div>
                </div>

                <!-- Program 2: Women Empowerment -->
                <div class="bg-white rounded-3xl overflow-hidden shadow-sm hover:shadow-2xl transition border border-slate-200 flex flex-col justify-between group">
                    <div>
                        <div class="h-52 overflow-hidden relative">
                            <img src="https://images.unsplash.com/photo-1573497019940-1c28c88b4f3e?auto=format&fit=crop&q=80&w=600" alt="Women Empowerment" class="w-full h-full object-cover group-hover:scale-105 transition duration-700">
                            <span class="absolute top-4 left-4 bg-brand-navy/90 text-brand-gold text-xs font-bold px-3.5 py-1 rounded-full uppercase tracking-wider shadow">Social Equity</span>
                        </div>
                        <div class="p-7 space-y-3">
                            <h3 class="text-xl font-bold text-brand-navy font-heading">Women Empowerment & SHGs</h3>
                            <p class="text-slate-600 text-sm leading-relaxed">
                                Fostering women's leadership, financial independence through Self-Help Groups, micro-enterprise training, and digital literacy.
                            </p>
                        </div>
                    </div>
                    <div class="px-7 pb-7 pt-2">
                        <a href="#contact" class="text-brand-aqua font-bold text-xs uppercase tracking-wider inline-flex items-center gap-1.5 hover:text-brand-navy transition">
                            Explore Project <i data-lucide="arrow-right" class="w-3.5 h-3.5"></i>
                        </a>
                    </div>
                </div>

                <!-- Program 3: Sustainable Livelihoods -->
                <div class="bg-white rounded-3xl overflow-hidden shadow-sm hover:shadow-2xl transition border border-slate-200 flex flex-col justify-between group">
                    <div>
                        <div class="h-52 overflow-hidden relative">
                            <img src="https://images.unsplash.com/photo-1500937386664-56d1dfef3854?auto=format&fit=crop&q=80&w=600" alt="Livelihoods" class="w-full h-full object-cover group-hover:scale-105 transition duration-700">
                            <span class="absolute top-4 left-4 bg-brand-navy/90 text-brand-gold text-xs font-bold px-3.5 py-1 rounded-full uppercase tracking-wider shadow">Economic Growth</span>
                        </div>
                        <div class="p-7 space-y-3">
                            <h3 class="text-xl font-bold text-brand-navy font-heading">Livelihoods & Farmer Producer Orgs</h3>
                            <p class="text-slate-600 text-sm leading-relaxed">
                                Empowering agrarian families via FPOs, organic farming aggregation, Kadaknath poultry value chains, and robust market linkages.
                            </p>
                        </div>
                    </div>
                    <div class="px-7 pb-7 pt-2">
                        <a href="#contact" class="text-brand-aqua font-bold text-xs uppercase tracking-wider inline-flex items-center gap-1.5 hover:text-brand-navy transition">
                            Explore Project <i data-lucide="arrow-right" class="w-3.5 h-3.5"></i>
                        </a>
                    </div>
                </div>

                <!-- Program 4: Watershed Management -->
                <div class="bg-white rounded-3xl overflow-hidden shadow-sm hover:shadow-2xl transition border border-slate-200 flex flex-col justify-between group">
                    <div>
                        <div class="h-52 overflow-hidden relative">
                            <img src="https://images.unsplash.com/photo-1464822759023-fed622ff2c3b?auto=format&fit=crop&q=80&w=600" alt="Watershed" class="w-full h-full object-cover group-hover:scale-105 transition duration-700">
                            <span class="absolute top-4 left-4 bg-brand-navy/90 text-brand-gold text-xs font-bold px-3.5 py-1 rounded-full uppercase tracking-wider shadow">Natural Resources</span>
                        </div>
                        <div class="p-7 space-y-3">
                            <h3 class="text-xl font-bold text-brand-navy font-heading">Integrated Watershed Management</h3>
                            <p class="text-slate-600 text-sm leading-relaxed">
                                Soil and moisture conservation, check dams, rainwater harvesting structures, and reviving local water tables for year-round farming.
                            </p>
                        </div>
                    </div>
                    <div class="px-7 pb-7 pt-2">
                        <a href="#contact" class="text-brand-aqua font-bold text-xs uppercase tracking-wider inline-flex items-center gap-1.5 hover:text-brand-navy transition">
                            Explore Project <i data-lucide="arrow-right" class="w-3.5 h-3.5"></i>
                        </a>
                    </div>
                </div>

                <!-- Program 5: Education & Capacity -->
                <div class="bg-white rounded-3xl overflow-hidden shadow-sm hover:shadow-2xl transition border border-slate-200 flex flex-col justify-between group">
                    <div>
                        <div class="h-52 overflow-hidden relative">
                            <img src="https://images.unsplash.com/photo-1497633762265-9d179a990aa6?auto=format&fit=crop&q=80&w=600" alt="Education" class="w-full h-full object-cover group-hover:scale-105 transition duration-700">
                            <span class="absolute top-4 left-4 bg-brand-navy/90 text-brand-gold text-xs font-bold px-3.5 py-1 rounded-full uppercase tracking-wider shadow">Youth & Education</span>
                        </div>
                        <div class="p-7 space-y-3">
                            <h3 class="text-xl font-bold text-brand-navy font-heading">Education & Youth Skills</h3>
                            <p class="text-slate-600 text-sm leading-relaxed">
                                Bridging learning gaps in remote tribal schools, digital skill training for youth, and community institutional capacity building.
                            </p>
                        </div>
                    </div>
                    <div class="px-7 pb-7 pt-2">
                        <a href="#contact" class="text-brand-aqua font-bold text-xs uppercase tracking-wider inline-flex items-center gap-1.5 hover:text-brand-navy transition">
                            Explore Project <i data-lucide="arrow-right" class="w-3.5 h-3.5"></i>
                        </a>
                    </div>
                </div>

                <!-- Program 6: Good Governance -->
                <div class="bg-white rounded-3xl overflow-hidden shadow-sm hover:shadow-2xl transition border border-slate-200 flex flex-col justify-between group">
                    <div>
                        <div class="h-52 overflow-hidden relative">
                            <img src="https://images.unsplash.com/photo-1517048676732-d65bc937f952?auto=format&fit=crop&q=80&w=600" alt="Governance" class="w-full h-full object-cover group-hover:scale-105 transition duration-700">
                            <span class="absolute top-4 left-4 bg-brand-navy/90 text-brand-gold text-xs font-bold px-3.5 py-1 rounded-full uppercase tracking-wider shadow">Rights & Policy</span>
                        </div>
                        <div class="p-7 space-y-3">
                            <h3 class="text-xl font-bold text-brand-navy font-heading">Good Governance & Entitlements</h3>
                            <p class="text-slate-600 text-sm leading-relaxed">
                                Ensuring awareness of public entitlements, legal rights, transparent local planning, and active participation in village governance.
                            </p>
                        </div>
                    </div>
                    <div class="px-7 pb-7 pt-2">
                        <a href="#contact" class="text-brand-aqua font-bold text-xs uppercase tracking-wider inline-flex items-center gap-1.5 hover:text-brand-navy transition">
                            Explore Project <i data-lucide="arrow-right" class="w-3.5 h-3.5"></i>
                        </a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Impact Dashboard Section -->
    <section id="impact" class="py-24 bg-brand-navy text-white relative overflow-hidden">
        <div class="max-w-7xl mx-auto px-4 sm:px-8 relative z-10">
            <div class="text-center max-w-3xl mx-auto mb-16 space-y-3">
                <span class="text-xs font-bold uppercase tracking-widest text-brand-gold">Measurable Social Impact</span>
                <h2 class="text-3xl sm:text-5xl font-extrabold tracking-tight font-heading">Our Footprint Across MP & Rajasthan</h2>
                <p class="text-slate-300 text-sm">Active in Jhabua, Dhar, Alirajpur (MP) and Banswara (Rajasthan), backed by a nationwide execution mandate.</p>
                <div class="w-24 h-1.5 bg-brand-gold mx-auto rounded-full"></div>
            </div>

            <!-- Stats Grid -->
            <div class="grid grid-cols-2 lg:grid-cols-4 gap-6 mb-16">
                <div class="glass-dark p-8 rounded-3xl text-center shadow-xl border border-brand-aqua/20">
                    <div class="text-4xl sm:text-6xl font-extrabold text-brand-gold mb-2 font-heading">4+</div>
                    <div class="text-slate-200 text-sm font-semibold">Core Tribal Districts</div>
                    <div class="text-slate-400 text-xs mt-1">MP & Rajasthan</div>
                </div>
                <div class="glass-dark p-8 rounded-3xl text-center shadow-xl border border-brand-aqua/20">
                    <div class="text-4xl sm:text-6xl font-extrabold text-brand-gold mb-2 font-heading">250+</div>
                    <div class="text-slate-200 text-sm font-semibold">Villages Reached</div>
                    <div class="text-slate-400 text-xs mt-1">Grassroots Transformation</div>
                </div>
                <div class="glass-dark p-8 rounded-3xl text-center shadow-xl border border-brand-aqua/20">
                    <div class="text-4xl sm:text-6xl font-extrabold text-brand-gold mb-2 font-heading">15k+</div>
                    <div class="text-slate-200 text-sm font-semibold">Saplings Planted</div>
                    <div class="text-slate-400 text-xs mt-1">Afforestation & Green Cover</div>
                </div>
                <div class="glass-dark p-8 rounded-3xl text-center shadow-xl border border-brand-aqua/20">
                    <div class="text-4xl sm:text-6xl font-extrabold text-brand-gold mb-2 font-heading">120+</div>
                    <div class="text-slate-200 text-sm font-semibold">SHGs & FPOs Formed</div>
                    <div class="text-slate-400 text-xs mt-1">Economic Self-Reliance</div>
                </div>
            </div>

            <!-- Operational Map / Footprint Card -->
            <div class="bg-brand-teal p-8 sm:p-10 rounded-3xl grid grid-cols-1 lg:grid-cols-12 gap-8 items-center border border-brand-aqua/30 shadow-2xl">
                <div class="lg:col-span-6 space-y-4">
                    <span class="text-brand-gold text-xs font-bold uppercase tracking-wider">Geographical Footprint</span>
                    <h3 class="text-2xl sm:text-3xl font-extrabold font-heading text-white">Grassroots Execution, National Mandate</h3>
                    <p class="text-slate-200 text-sm leading-relaxed">
                        Tailored specifically to the Bhil tribal topography. We partner directly with village panchayats and youth cooperatives to guarantee high accountability and transparent ESG metrics.
                    </p>
                    <div class="pt-2 flex flex-wrap gap-2">
                        <span class="px-3.5 py-1.5 bg-brand-navy text-brand-gold text-xs font-bold rounded-xl border border-brand-aqua/40">Jhabua (MP)</span>
                        <span class="px-3.5 py-1.5 bg-brand-navy text-brand-gold text-xs font-bold rounded-xl border border-brand-aqua/40">Dhar (MP)</span>
                        <span class="px-3.5 py-1.5 bg-brand-navy text-brand-gold text-xs font-bold rounded-xl border border-brand-aqua/40">Alirajpur (MP)</span>
                        <span class="px-3.5 py-1.5 bg-brand-navy text-brand-gold text-xs font-bold rounded-xl border border-brand-aqua/40">Banswara (RJ)</span>
                    </div>
                </div>
                <div class="lg:col-span-6 bg-brand-navy p-8 rounded-2xl border border-brand-aqua/30 flex flex-col justify-center items-center text-center">
                    <i data-lucide="globe-2" class="w-16 h-16 text-brand-gold mb-4 opacity-90 animate-pulse"></i>
                    <h4 class="font-bold text-xl mb-2 font-heading">Pan-India CSR & Welfare Ready</h4>
                    <p class="text-slate-300 text-xs max-w-md leading-relaxed">Fully compliant for national-level scaling, corporate CSR partnerships, and multi-state development grants under statutory regulations.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Stories of Change -->
    <section id="stories" class="py-24 bg-white">
        <div class="max-w-7xl mx-auto px-4 sm:px-8">
            <div class="text-center max-w-3xl mx-auto mb-16 space-y-3">
                <span class="text-xs font-bold uppercase tracking-widest text-brand-aqua">Voices of Impact</span>
                <h2 class="text-3xl sm:text-5xl font-extrabold tracking-tight text-brand-navy font-heading">Stories of Real Transformation</h2>
                <div class="w-24 h-1.5 bg-brand-gold mx-auto rounded-full"></div>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
                <div class="bg-slate-50 border border-slate-200 rounded-3xl p-8 sm:p-10 shadow-sm hover:shadow-xl transition flex flex-col justify-between">
                    <div class="space-y-4">
                        <div class="flex items-center gap-4">
                            <img src="https://images.unsplash.com/photo-1534528741775-53994a69daeb?auto=format&fit=crop&q=80&w=200" alt="Kavita Bhil" class="w-14 h-14 rounded-full object-cover border-2 border-brand-gold shadow">
                            <div>
                                <h4 class="font-bold text-brand-navy font-heading text-lg">Kavita Bhil</h4>
                                <p class="text-xs text-brand-aqua font-semibold">SHG Leader & FPO Member, Jhabua</p>
                            </div>
                        </div>
                        <p class="text-slate-600 text-sm leading-relaxed italic">
                            "Before BASS India introduced us to Self-Help Groups and modern organic farming, our household depended entirely on erratic monsoon rains. Today, through our FPO and watershed training, I lead a cooperative of 40 women and secure a dignified livelihood."
                        </p>
                    </div>
                    <div class="pt-6 border-t border-slate-200 flex justify-between items-center text-xs font-bold text-slate-500">
                        <span>Thematic: Women & Livelihoods</span>
                        <span class="text-brand-aqua hover:underline cursor-pointer">Read Full Story →</span>
                    </div>
                </div>

                <div class="bg-slate-50 border border-slate-200 rounded-3xl p-8 sm:p-10 shadow-sm hover:shadow-xl transition flex flex-col justify-between">
                    <div class="space-y-4">
                        <div class="flex items-center gap-4">
                            <img src="https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?auto=format&fit=crop&q=80&w=200" alt="Ramesh Damor" class="w-14 h-14 rounded-full object-cover border-2 border-brand-gold shadow">
                            <div>
                                <h4 class="font-bold text-brand-navy font-heading text-lg">Ramesh Damor</h4>
                                <p class="text-xs text-brand-aqua font-semibold">Afforestation Lead, Banswara</p>
                            </div>
                        </div>
                        <p class="text-slate-600 text-sm leading-relaxed italic">
                            "Our hills were severely eroded and barren. BASS India mobilized our village youth to plant native fruit and medicinal saplings while building check dams. Groundwater has revived, and our green cover is fully restored."
                        </p>
                    </div>
                    <div class="pt-6 border-t border-slate-200 flex justify-between items-center text-xs font-bold text-slate-500">
                        <span>Thematic: Climate & Afforestation</span>
                        <span class="text-brand-aqua hover:underline cursor-pointer">Read Full Story →</span>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Corporate CSR Partnership (Get Involved) -->
    <section id="get-involved" class="py-24 bg-slate-100">
        <div class="max-w-7xl mx-auto px-4 sm:px-8">
            <div class="bg-brand-navy text-white rounded-3xl p-8 sm:p-14 lg:p-16 relative overflow-hidden shadow-2xl border border-brand-teal">
                <div class="absolute right-0 bottom-0 opacity-10 translate-x-10 translate-y-10">
                    <i data-lucide="hand-heart" class="w-96 h-96 text-white"></i>
                </div>
                
                <div class="relative z-10 grid grid-cols-1 lg:grid-cols-12 gap-12 items-center">
                    <div class="lg:col-span-7 space-y-6">
                        <span class="text-xs font-bold uppercase tracking-widest text-brand-gold">Get Involved</span>
                        <h2 class="text-3xl sm:text-5xl font-extrabold tracking-tight font-heading">Partner for CSR or Join Volunteer Network</h2>
                        <p class="text-slate-300 text-sm leading-relaxed">
                            Whether you're a corporate CSR head looking for verified ESG metrics, or a young changemaker wanting to contribute digital skills or field support—BASS India offers transparent, impact-driven collaboration.
                        </p>
                        <div class="flex flex-wrap gap-4 pt-2">
                            <a href="#contact" class="bg-brand-gold hover:bg-amber-400 text-brand-navy font-extrabold px-7 py-3.5 rounded-2xl transition shadow">
                                Corporate CSR Inquiry
                            </a>
                            <a href="#donate" class="bg-white/10 hover:bg-white/20 border border-white/25 text-white font-bold px-7 py-3.5 rounded-2xl transition">
                                Donate For 80G Tax Exemption
                            </a>
                        </div>
                    </div>
                    
                    <div class="lg:col-span-5 glass-dark p-6 sm:p-8 rounded-3xl border border-brand-aqua/30 shadow-xl">
                        <h3 class="font-bold text-lg mb-4 text-brand-gold font-heading">Why Partner With BASS India?</h3>
                        <ul class="space-y-3 text-sm text-slate-200">
                            <li class="flex items-start gap-2.5">
                                <i data-lucide="check-circle" class="w-4 h-4 text-brand-gold shrink-0 mt-0.5"></i>
                                <span>100% Statutory Compliance (80G, 12A, CSR-1)</span>
                            </li>
                            <li class="flex items-start gap-2.5">
                                <i data-lucide="check-circle" class="w-4 h-4 text-brand-gold shrink-0 mt-0.5"></i>
                                <span>Real-Time ESG & Environmental Impact Tracking</span>
                            </li>
                            <li class="flex items-start gap-2.5">
                                <i data-lucide="check-circle" class="w-4 h-4 text-brand-gold shrink-0 mt-0.5"></i>
                                <span>Deep Grassroots Access Across MP & Rajasthan</span>
                            </li>
                            <li class="flex items-start gap-2.5">
                                <i data-lucide="check-circle" class="w-4 h-4 text-brand-gold shrink-0 mt-0.5"></i>
                                <span>Transparent Donor Dashboards for Modern Philanthropy</span>
                            </li>
                        </ul>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Resources & Publications -->
    <section id="resources" class="py-24 bg-white">
        <div class="max-w-7xl mx-auto px-4 sm:px-8">
            <div class="text-center max-w-3xl mx-auto mb-16 space-y-3">
                <span class="text-xs font-bold uppercase tracking-widest text-brand-aqua">Knowledge & Reports</span>
                <h2 class="text-3xl sm:text-5xl font-extrabold tracking-tight text-brand-navy font-heading">Resources & Publications</h2>
                <div class="w-24 h-1.5 bg-brand-gold mx-auto rounded-full"></div>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
                <div class="bg-slate-50 border border-slate-200 p-8 rounded-3xl space-y-4 hover:border-brand-aqua transition group shadow-sm">
                    <div class="w-12 h-12 rounded-2xl bg-brand-navy text-brand-gold flex items-center justify-center shadow">
                        <i data-lucide="file-text" class="w-6 h-6"></i>
                    </div>
                    <h3 class="font-bold text-xl text-brand-navy font-heading">Annual Impact Report 2025-26</h3>
                    <p class="text-xs text-slate-600 leading-relaxed">Comprehensive breakdown of our afforestation milestones, SHG financial turnovers, and regional livelihood outcomes.</p>
                    <a href="#contact" class="text-xs font-bold text-brand-aqua uppercase tracking-wider inline-flex items-center gap-1 group-hover:underline">Download PDF (PDF) →</a>
                </div>
                <div class="bg-slate-50 border border-slate-200 p-8 rounded-3xl space-y-4 hover:border-brand-aqua transition group shadow-sm">
                    <div class="w-12 h-12 rounded-2xl bg-brand-navy text-brand-gold flex items-center justify-center shadow">
                        <i data-lucide="file-text" class="w-6 h-6"></i>
                    </div>
                    <h3 class="font-bold text-xl text-brand-navy font-heading">Climate Resilience Brief</h3>
                    <p class="text-xs text-slate-600 leading-relaxed">Technical documentation on watershed management and community-led afforestation models across Jhabua district.</p>
                    <a href="#contact" class="text-xs font-bold text-brand-aqua uppercase tracking-wider inline-flex items-center gap-1 group-hover:underline">Download PDF (PDF) →</a>
                </div>
                <div class="bg-slate-50 border border-slate-200 p-8 rounded-3xl space-y-4 hover:border-brand-aqua transition group shadow-sm">
                    <div class="w-12 h-12 rounded-2xl bg-brand-navy text-brand-gold flex items-center justify-center shadow">
                        <i data-lucide="file-text" class="w-6 h-6"></i>
                    </div>
                    <h3 class="font-bold text-xl text-brand-navy font-heading">Women FPO Handbook</h3>
                    <p class="text-xs text-slate-600 leading-relaxed">Guidebook on structuring, managing, and scaling women-led Farmer Producer Organizations at the grassroots level.</p>
                    <a href="#contact" class="text-xs font-bold text-brand-aqua uppercase tracking-wider inline-flex items-center gap-1 group-hover:underline">Download PDF (PDF) →</a>
                </div>
            </div>
        </div>
    </section>

    <!-- Donation Section -->
    <section id="donate" class="py-24 bg-slate-100 border-t border-slate-200">
        <div class="max-w-4xl mx-auto px-4 sm:px-8">
            <div class="bg-white border border-slate-200 rounded-3xl p-8 sm:p-12 shadow-2xl">
                <div class="text-center max-w-xl mx-auto mb-10 space-y-3">
                    <span class="text-xs font-bold uppercase tracking-widest text-brand-aqua">Support Our Cause</span>
                    <h2 class="text-3xl sm:text-4xl font-extrabold text-brand-navy font-heading">Empower a Tribal Family Today</h2>
                    <p class="text-slate-600 text-sm">Contributions are fully eligible for tax exemption under Section 80G of the Income Tax Act.</p>
                </div>

                <form onsubmit="handleDonation(event)" class="space-y-6">
                    <div class="grid grid-cols-3 gap-4">
                        <button type="button" onclick="selectAmount(1000)" class="donation-btn py-3.5 border-2 border-brand-aqua bg-sky-50 text-brand-navy font-bold rounded-2xl text-center transition shadow-sm">₹1,000</button>
                        <button type="button" onclick="selectAmount(5000)" class="donation-btn py-3.5 border-2 border-slate-200 hover:border-brand-aqua text-slate-800 font-bold rounded-2xl text-center transition">₹5,000</button>
                        <button type="button" onclick="selectAmount(10000)" class="donation-btn py-3.5 border-2 border-slate-200 hover:border-brand-aqua text-slate-800 font-bold rounded-2xl text-center transition">₹10,000</button>
                    </div>

                    <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
                        <div>
                            <label class="block text-xs font-bold text-slate-700 uppercase mb-1.5">Full Name</label>
                            <input type="text" required class="w-full px-4 py-3.5 rounded-2xl border border-slate-300 focus:ring-2 focus:ring-brand-aqua focus:outline-none text-sm bg-slate-50" placeholder="Your Name">
                        </div>
                        <div>
                            <label class="block text-xs font-bold text-slate-700 uppercase mb-1.5">Email Address</label>
                            <input type="email" required class="w-full px-4 py-3.5 rounded-2xl border border-slate-300 focus:ring-2 focus:ring-brand-aqua focus:outline-none text-sm bg-slate-50" placeholder="name@example.com">
                        </div>
                    </div>

                    <div>
                        <label class="block text-xs font-bold text-slate-700 uppercase mb-1.5">PAN Number (Required for 80G Tax Exemption Receipt)</label>
                        <input type="text" class="w-full px-4 py-3.5 rounded-2xl border border-slate-300 focus:ring-2 focus:ring-brand-aqua focus:outline-none text-sm uppercase bg-slate-50" placeholder="ABCDE1234F">
                    </div>

                    <button type="submit" class="w-full bg-brand-gold hover:bg-amber-400 text-brand-navy font-extrabold py-4 rounded-2xl shadow-xl transition text-center text-sm uppercase tracking-wider flex items-center justify-center gap-2 transform hover:-translate-y-0.5">
                        <i data-lucide="lock" class="w-4 h-4"></i> Proceed Securely to Donate
                    </button>
                </form>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="py-24 bg-white border-t border-slate-200">
        <div class="max-w-7xl mx-auto px-4 sm:px-8">
            <div class="grid grid-cols-1 lg:grid-cols-12 gap-12">
                <div class="lg:col-span-5 space-y-6">
                    <span class="text-xs font-bold uppercase tracking-widest text-brand-aqua">Get in Touch</span>
                    <h2 class="text-3xl font-extrabold tracking-tight text-brand-navy font-heading">Contact BASS India</h2>
                    <p class="text-slate-600 text-sm leading-relaxed">
                        Whether you are a volunteer, corporate CSR leader, or government stakeholder, our doors are open. Let's build a sustainable future together.
                    </p>

                    <div class="space-y-4 pt-4 text-sm text-slate-700">
                        <div class="flex items-start gap-3.5">
                            <div class="w-11 h-11 rounded-2xl bg-brand-navy text-brand-gold flex items-center justify-center shrink-0 shadow">
                                <i data-lucide="map-pin" class="w-5 h-5"></i>
                            </div>
                            <div>
                                <strong class="block text-brand-navy font-heading">Head Office</strong>
                                <span class="text-slate-600">Jhabua District, Madhya Pradesh, India (Nationwide Operations Permitted)</span>
                            </div>
                        </div>
                        <div class="flex items-center gap-3.5">
                            <div class="w-11 h-11 rounded-2xl bg-brand-navy text-brand-gold flex items-center justify-center shrink-0 shadow">
                                <i data-lucide="mail" class="w-5 h-5"></i>
                            </div>
                            <div>
                                <strong class="block text-brand-navy font-heading">Email Address</strong>
                                <span class="text-slate-600">contact@bassindia.org.in | csr@bassindia.org.in</span>
                            </div>
                        </div>
                        <div class="flex items-center gap-3.5">
                            <div class="w-11 h-11 rounded-2xl bg-brand-navy text-brand-gold flex items-center justify-center shrink-0 shadow">
                                <i data-lucide="phone" class="w-5 h-5"></i>
                            </div>
                            <div>
                                <strong class="block text-brand-navy font-heading">Phone</strong>
                                <span class="text-slate-600">+91 (0) 2652 XXX XXX / Dedicated Helpline</span>
                            </div>
                        </div>
                    </div>
                </div>

                <div class="lg:col-span-7 bg-slate-50 border border-slate-200 p-8 sm:p-10 rounded-3xl shadow-sm">
                    <h3 class="text-2xl font-bold text-brand-navy mb-6 font-heading">Send Us a Message</h3>
                    <form onsubmit="handleContact(event)" class="space-y-4">
                        <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
                            <div>
                                <label class="block text-xs font-bold text-slate-700 uppercase mb-1.5">Your Name</label>
                                <input type="text" required class="w-full px-4 py-3.5 rounded-2xl border border-slate-300 focus:ring-2 focus:ring-brand-aqua focus:outline-none text-sm bg-white" placeholder="Full Name">
                            </div>
                            <div>
                                <label class="block text-xs font-bold text-slate-700 uppercase mb-1.5">Email Address</label>
                                <input type="email" required class="w-full px-4 py-3.5 rounded-2xl border border-slate-300 focus:ring-2 focus:ring-brand-aqua focus:outline-none text-sm bg-white" placeholder="email@example.com">
                            </div>
                        </div>
                        <div>
                            <label class="block text-xs font-bold text-slate-700 uppercase mb-1.5">Inquiry Category</label>
                            <select class="w-full px-4 py-3.5 rounded-2xl border border-slate-300 focus:ring-2 focus:ring-brand-aqua focus:outline-none text-sm bg-white">
                                <option>Corporate CSR Partnership</option>
                                <option>Afforestation & Climate Project Collaboration</option>
                                <option>Women SHG / FPO Inquiry</option>
                                <option>Volunteer & Outreach</option>
                                <option>General Information</option>
                            </select>
                        </div>
                        <div>
                            <label class="block text-xs font-bold text-slate-700 uppercase mb-1.5">Message</label>
                            <textarea rows="4" required class="w-full px-4 py-3.5 rounded-2xl border border-slate-300 focus:ring-2 focus:ring-brand-aqua focus:outline-none text-sm bg-white" placeholder="How can we collaborate?"></textarea>
                        </div>
                        <button type="submit" class="w-full bg-brand-navy hover:bg-brand-teal text-white font-bold py-4 rounded-2xl transition text-sm uppercase tracking-wider shadow-lg">
                            Send Message
                        </button>
                    </form>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="bg-brand-navy text-slate-300 py-16 border-t border-brand-teal">
        <div class="max-w-7xl mx-auto px-4 sm:px-8 grid grid-cols-1 md:grid-cols-2 lg:grid-cols-5 gap-10 mb-12">
            <div class="lg:col-span-2 space-y-4">
                <div class="flex items-center gap-3">
                    <div class="w-10 h-10 rounded-full overflow-hidden border border-brand-aqua bg-white p-0.5">
                        <img src="BASS India Logo.jpeg" alt="BASS India Logo" class="w-full h-full object-cover rounded-full">
                    </div>
                    <span class="text-xl font-extrabold tracking-tight text-white font-heading">BASS India</span>
                </div>
                <p class="text-xs text-slate-400 leading-relaxed max-w-sm">
                    Bhilang Aadivaasee Saamaajik Samiti (BASS India) is an NGO dedicated to grassroots development, women empowerment, climate action, and sustainable livelihoods across India, rooted in Jhabua, MP.
                </p>
                <div class="text-xs text-slate-300">
                    <p><strong>Registrations:</strong> 80G, 12A & CSR-1 Certified</p>
                </div>
            </div>

            <div>
                <h4 class="font-bold text-white text-sm mb-4 uppercase tracking-wider font-heading">Quick Links</h4>
                <ul class="space-y-2 text-xs">
                    <li><a href="#home" class="hover:text-brand-sky transition">Home</a></li>
                    <li><a href="#about" class="hover:text-brand-sky transition">About Us</a></li>
                    <li><a href="#programs" class="hover:text-brand-sky transition">Core Programs</a></li>
                    <li><a href="#impact" class="hover:text-brand-sky transition">Impact Dashboard</a></li>
                    <li><a href="#stories" class="hover:text-brand-sky transition">Stories of Change</a></li>
                </ul>
            </div>

            <div>
                <h4 class="font-bold text-white text-sm mb-4 uppercase tracking-wider font-heading">Thematic Areas</h4>
                <ul class="space-y-2 text-xs">
                    <li><a href="#programs" class="hover:text-brand-sky transition">Climate & Afforestation</a></li>
                    <li><a href="#programs" class="hover:text-brand-sky transition">Women Empowerment & SHGs</a></li>
                    <li><a href="#programs" class="hover:text-brand-sky transition">Livelihoods & FPOs</a></li>
                    <li><a href="#programs" class="hover:text-brand-sky transition">Watershed Management</a></li>
                    <li><a href="#programs" class="hover:text-brand-sky transition">Good Governance</a></li>
                </ul>
            </div>

            <div>
                <h4 class="font-bold text-white text-sm mb-4 uppercase tracking-wider font-heading">Newsletter</h4>
                <p class="text-xs text-slate-400 mb-3">Get quarterly ESG updates and impact briefs.</p>
                <form onsubmit="handleNewsletter(event)" class="space-y-2">
                    <input type="email" required placeholder="Your email address" class="w-full px-3.5 py-2.5 rounded-xl bg-brand-teal border border-brand-aqua/30 text-xs text-white focus:outline-none focus:ring-1 focus:ring-brand-gold">
                    <button type="submit" class="w-full bg-brand-gold hover:bg-amber-400 text-brand-navy font-bold py-2.5 rounded-xl text-xs uppercase tracking-wider transition shadow">Subscribe</button>
                </form>
            </div>
        </div>

        <div class="max-w-7xl mx-auto px-4 sm:px-8 pt-8 border-t border-brand-teal flex flex-col sm:flex-row justify-between items-center gap-4 text-xs text-slate-400">
            <p>© 2026 Bhilang Aadivaasee Saamaajik Samiti (BASS India). All rights reserved.</p>
            <div class="flex gap-6">
                <a href="#" class="hover:text-brand-sky transition">Privacy Policy</a>
                <a href="#" class="hover:text-brand-sky transition">Terms of Use</a>
                <a href="#" class="hover:text-brand-sky transition">Disclaimer</a>
            </div>
        </div>
    </footer>

    <!-- JavaScript Interactivity -->
    <script>
        // Initialize Lucide Icons
        lucide.createIcons();

        // Mobile Menu Toggle
        function toggleMobileMenu() {
            const menu = document.getElementById('mobileMenu');
            menu.classList.toggle('hidden');
        }

        // Hero Slideshow Logic
        let slideIndex = 0;
        const slides = document.querySelectorAll('.slide');
        const dots = document.querySelectorAll('.dot');

        function showSlide(n) {
            slides.forEach(slide => slide.classList.remove('active'));
            dots.forEach(dot => dot.classList.remove('bg-brand-gold'));
            dots.forEach(dot => dot.classList.add('bg-slate-500'));

            slideIndex = (n + slides.length) % slides.length;
            slides[slideIndex].classList.add('active');
            dots[slideIndex].classList.remove('bg-slate-500');
            dots[slideIndex].classList.add('bg-brand-gold');
        }

        function nextSlide() { showSlide(slideIndex + 1); }
        function prevSlide() { showSlide(slideIndex - 1); }
        function currentSlide(n) { showSlide(n); }

        // Auto play slideshow every 5 seconds
        setInterval(nextSlide, 5000);

        // Donation Amount Selector
        function selectAmount(amount) {
            const buttons = document.querySelectorAll('.donation-btn');
            buttons.forEach(btn => {
                btn.classList.remove('border-brand-aqua', 'bg-sky-50', 'text-brand-navy');
                btn.classList.add('border-slate-200', 'text-slate-800');
            });
            event.target.classList.remove('border-slate-200', 'text-slate-800');
            event.target.classList.add('border-brand-aqua', 'bg-sky-50', 'text-brand-navy');
        }

        // Form Handlers
        function handleDonation(e) {
            e.preventDefault();
            alert('Thank you for supporting BASS India! Secure payment gateway integration will process your 80G tax-exempt donation.');
        }

        function handleContact(e) {
            e.preventDefault();
            alert('Thank you for reaching out to BASS India. Our team will get back to you shortly.');
            e.target.reset();
        }

        function handleNewsletter(e) {
            e.preventDefault();
            alert('Thank you for subscribing to BASS India impact updates!');
            e.target.reset();
        }

        // Language Toggle Simulation
        let isHindi = false;
        function toggleLanguage() {
            isHindi = !isHindi;
            const heroTitle = document.getElementById('heroTitle');
            const heroSubtitle = document.getElementById('heroSubtitle');
            const langBtn = document.getElementById('langBtn');

            if (isHindi) {
                heroTitle.innerHTML = 'आदिवासी भविष्य का पुनर्निर्माण, <span class="text-brand-sky">पर्यावरण का संरक्षण।</span>';
                heroSubtitle.innerHTML = 'भिलांग आदिवासी सामाजिक समिति (BASS India) मध्य प्रदेश और राजस्थान के आदिवासी अंचलों में जलवायु कार्रवाई, वनीकरण, महिला उद्यमिता और सतत आजीविका के लिए प्रतिबद्ध है।';
                langBtn.innerText = 'English / हिंदी';
            } else {
                heroTitle.innerHTML = 'Reimagining Tribal Futures, <span class="text-brand-sky">Restoring Nature.</span>';
                heroSubtitle.innerHTML = 'Bhilang Aadivaasee Saamaajik Samiti (BASS India) combines indigenous wisdom with modern tech and climate action. Fueling grassroots women entrepreneurship, watershed restoration, and afforestation across Jhabua, Dhar, Alirajpur, and Banswara.';
                langBtn.innerText = 'हिंदी / English';
            }
        }
    </script>
</body>
</html>
