<!DOCTYPE html>
<html lang="en" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mehul Kumar Sinha | Data Engineer</title>
    <meta name="description" content="Portfolio of Mehul Kumar Sinha - Data Engineer specializing in scalable architectures and distributed systems.">
    
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/gsap.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/ScrollTrigger.min.js"></script>
    <script src="https://unpkg.com/lucide@latest"></script>
    
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600&family=Space+Grotesk:wght@300;400;500;600;700&display=swap" rel="stylesheet">

    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        deep: {
                            900: '#0a0a0f',
                            800: '#111118',
                            700: '#1a1a24',
                        },
                        cyan: {
                            400: '#22d3ee',
                            500: '#06b6d4',
                            glow: 'rgba(34, 211, 238, 0.15)',
                        },
                        violet: {
                            400: '#a78bfa',
                            glow: 'rgba(167, 139, 250, 0.15)',
                        }
                    },
                    fontFamily: {
                        sans: ['Inter', 'sans-serif'],
                        display: ['Space Grotesk', 'sans-serif'],
                    }
                }
            }
        }
    </script>

    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', sans-serif;
            background-color: #0a0a0f;
            color: #e2e8f0;
            overflow-x: hidden;
        }

        /* Subtle Grid Background */
        .bg-grid {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-image: 
                linear-gradient(rgba(34, 211, 238, 0.03) 1px, transparent 1px),
                linear-gradient(90deg, rgba(34, 211, 238, 0.03) 1px, transparent 1px);
            background-size: 60px 60px;
            pointer-events: none;
            z-index: -1;
            mask-image: radial-gradient(circle at center, black 40%, transparent 100%);
        }

        /* Ambient Gradient Orbs */
        .ambient-orb {
            position: fixed;
            border-radius: 50%;
            filter: blur(100px);
            opacity: 0.15;
            pointer-events: none;
            z-index: -1;
            animation: float 20s infinite ease-in-out;
        }

        .orb-1 {
            width: 600px;
            height: 600px;
            background: radial-gradient(circle, #22d3ee, transparent 70%);
            top: -200px;
            right: -200px;
            animation-delay: 0s;
        }

        .orb-2 {
            width: 500px;
            height: 500px;
            background: radial-gradient(circle, #a78bfa, transparent 70%);
            bottom: -100px;
            left: -100px;
            animation-delay: -10s;
        }

        @keyframes float {
            0%, 100% { transform: translate(0, 0) scale(1); }
            33% { transform: translate(30px, -30px) scale(1.1); }
            66% { transform: translate(-20px, 20px) scale(0.9); }
        }

        /* Glass Cards */
        .glass-card {
            background: rgba(17, 17, 24, 0.6);
            backdrop-filter: blur(12px);
            border: 1px solid rgba(255, 255, 255, 0.05);
            transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
        }

        .glass-card:hover {
            border-color: rgba(34, 211, 238, 0.2);
            box-shadow: 0 0 30px rgba(34, 211, 238, 0.05);
            transform: translateY(-2px);
        }

        /* Custom Cursor */
        .cursor-dot,
        .cursor-outline {
            position: fixed;
            top: 0;
            left: 0;
            transform: translate(-50%, -50%);
            border-radius: 50%;
            z-index: 9999;
            pointer-events: none;
        }

        .cursor-dot {
            width: 5px;
            height: 5px;
            background-color: #22d3ee;
        }

        .cursor-outline {
            width: 30px;
            height: 30px;
            border: 1px solid rgba(34, 211, 238, 0.5);
            transition: width 0.2s, height 0.2s, background-color 0.2s;
        }

        .cursor-outline.hover {
            width: 50px;
            height: 50px;
            background-color: rgba(34, 211, 238, 0.05);
            border-color: #22d3ee;
        }

        /* Loading Screen */
        .loader {
            position: fixed;
            inset: 0;
            background: #0a0a0f;
            z-index: 10000;
            display: flex;
            justify-content: center;
            align-items: center;
            transition: opacity 0.6s ease, visibility 0.6s;
        }

        .loader.hidden {
            opacity: 0;
            visibility: hidden;
        }

        .loader-content {
            text-align: center;
        }

        .loader-bar {
            width: 200px;
            height: 2px;
            background: rgba(255, 255, 255, 0.1);
            margin-top: 20px;
            position: relative;
            overflow: hidden;
            border-radius: 2px;
        }

        .loader-progress {
            position: absolute;
            left: 0;
            top: 0;
            height: 100%;
            width: 0%;
            background: linear-gradient(90deg, #22d3ee, #a78bfa);
            transition: width 0.3s ease;
        }

        /* Navigation */
        .nav-glass {
            background: rgba(10, 10, 15, 0.8);
            backdrop-filter: blur(20px);
            border-bottom: 1px solid rgba(255, 255, 255, 0.05);
        }

        .nav-link {
            position: relative;
            color: rgba(226, 232, 240, 0.6);
            transition: color 0.3s;
        }

        .nav-link::after {
            content: '';
            position: absolute;
            bottom: -4px;
            left: 0;
            width: 0;
            height: 1px;
            background: #22d3ee;
            transition: width 0.3s;
            box-shadow: 0 0 10px rgba(34, 211, 238, 0.5);
        }

        .nav-link:hover {
            color: #e2e8f0;
        }

        .nav-link:hover::after {
            width: 100%;
        }

        /* Buttons */
        .btn-primary {
            background: linear-gradient(135deg, rgba(34, 211, 238, 0.1), rgba(167, 139, 250, 0.1));
            border: 1px solid rgba(34, 211, 238, 0.3);
            color: #22d3ee;
            transition: all 0.3s;
            position: relative;
            overflow: hidden;
        }

        .btn-primary::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(34, 211, 238, 0.2), transparent);
            transition: left 0.5s;
        }

        .btn-primary:hover::before {
            left: 100%;
        }

        .btn-primary:hover {
            border-color: #22d3ee;
            box-shadow: 0 0 20px rgba(34, 211, 238, 0.2);
            color: #fff;
        }

        /* Section Reveals */
        .reveal {
            opacity: 0;
            transform: translateY(30px);
            transition: opacity 0.8s ease, transform 0.8s ease;
        }

        .reveal.active {
            opacity: 1;
            transform: translateY(0);
        }

        /* Timeline */
        .timeline-line {
            position: absolute;
            left: 0;
            top: 0;
            bottom: 0;
            width: 1px;
            background: linear-gradient(to bottom, #22d3ee, #a78bfa, transparent);
            opacity: 0.3;
        }

        .timeline-dot {
            position: absolute;
            left: -4px;
            top: 24px;
            width: 9px;
            height: 9px;
            border-radius: 50%;
            background: #0a0a0f;
            border: 2px solid #22d3ee;
            box-shadow: 0 0 10px rgba(34, 211, 238, 0.5);
        }

        /* Audio Player */
        .audio-control {
            position: fixed;
            bottom: 2rem;
            right: 2rem;
            z-index: 40;
            width: 48px;
            height: 48px;
            border-radius: 50%;
            background: rgba(17, 17, 24, 0.8);
            border: 1px solid rgba(34, 211, 238, 0.2);
            backdrop-filter: blur(10px);
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            transition: all 0.3s;
        }

        .audio-control:hover {
            border-color: #22d3ee;
            box-shadow: 0 0 20px rgba(34, 211, 238, 0.2);
            transform: scale(1.1);
        }

        .audio-control.playing {
            animation: pulse-glow 2s infinite;
        }

        @keyframes pulse-glow {
            0%, 100% { box-shadow: 0 0 0 0 rgba(34, 211, 238, 0.4); }
            50% { box-shadow: 0 0 0 10px rgba(34, 211, 238, 0); }
        }

        /* Scroll Progress */
        .progress-bar {
            position: fixed;
            top: 0;
            left: 0;
            height: 2px;
            background: linear-gradient(90deg, #22d3ee, #a78bfa);
            z-index: 9999;
            box-shadow: 0 0 10px rgba(34, 211, 238, 0.5);
        }

        /* Skill Tags */
        .skill-tag {
            background: rgba(34, 211, 238, 0.05);
            border: 1px solid rgba(34, 211, 238, 0.1);
            color: rgba(226, 232, 240, 0.8);
            transition: all 0.3s;
        }

        .skill-tag:hover {
            background: rgba(34, 211, 238, 0.1);
            border-color: rgba(34, 211, 238, 0.3);
            color: #22d3ee;
            transform: translateY(-1px);
        }

        /* Gradient Text */
        .gradient-text {
            background: linear-gradient(135deg, #22d3ee 0%, #a78bfa 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        @media (max-width: 768px) {
            .cursor-dot, .cursor-outline { display: none; }
            body { cursor: auto; }
        }
    </style>
</head>
<body class="antialiased selection:bg-cyan-500/30 selection:text-white">

    <!-- Loading Screen -->
    <div class="loader" id="loader">
        <div class="loader-content">
            <div class="font-display text-2xl tracking-widest text-cyan-400 mb-2">MKS</div>
            <div class="text-xs text-gray-500 tracking-[0.3em] uppercase">Initializing</div>
            <div class="loader-bar">
                <div class="loader-progress" id="loader-progress"></div>
            </div>
        </div>
    </div>

    <!-- Custom Cursor -->
    <div class="cursor-dot" id="cursor-dot"></div>
    <div class="cursor-outline" id="cursor-outline"></div>

    <!-- Progress Bar -->
    <div class="progress-bar" id="progress-bar" style="width: 0%"></div>

    <!-- Background Elements -->
    <div class="bg-grid"></div>
    <div class="ambient-orb orb-1"></div>
    <div class="ambient-orb orb-2"></div>

    <!-- Audio Control -->
    <div class="audio-control" id="audio-control" title="Toggle Ambient Sound">
        <i data-lucide="volume-2" class="w-5 h-5 text-cyan-400" id="audio-icon"></i>
    </div>

    <!-- Ambient Audio -->
    <audio id="ambient-audio" loop>
        <source src="https://cdn.pixabay.com/download/audio/2022/05/27/audio_1808fbf07a.mp3?filename=soft-piano-100-bpm-121529.mp3" type="audio/mpeg">
    </audio>

    <!-- Navigation -->
    <nav class="fixed top-0 w-full z-50 transition-all duration-300 py-6" id="navbar">
        <div class="max-w-7xl mx-auto px-6 flex justify-between items-center">
            <a href="#home" class="font-display text-xl tracking-widest text-white hover-target">
                MKS<span class="text-cyan-400">.</span>
            </a>
            
            <div class="hidden md:flex items-center space-x-8">
                <a href="#about" class="nav-link text-sm uppercase tracking-widest hover-target">About</a>
                <a href="#experience" class="nav-link text-sm uppercase tracking-widest hover-target">Experience</a>
                <a href="#skills" class="nav-link text-sm uppercase tracking-widest hover-target">Skills</a>
                <a href="#contact" class="btn-primary px-6 py-2 rounded-full text-sm uppercase tracking-widest hover-target">Contact</a>
            </div>

            <button class="md:hidden text-cyan-400 hover-target" id="mobile-menu-btn">
                <i data-lucide="menu" class="w-6 h-6"></i>
            </button>
        </div>
    </nav>

    <!-- Mobile Menu -->
    <div class="fixed inset-0 bg-deep-900/98 backdrop-blur-xl z-40 transform translate-x-full transition-transform duration-500 ease-out" id="mobile-menu">
        <div class="flex flex-col items-center justify-center h-full space-y-8">
            <a href="#about" class="font-display text-2xl text-white hover:text-cyan-400 transition-colors mobile-link">About</a>
            <a href="#experience" class="font-display text-2xl text-white hover:text-cyan-400 transition-colors mobile-link">Experience</a>
            <a href="#skills" class="font-display text-2xl text-white hover:text-cyan-400 transition-colors mobile-link">Skills</a>
            <a href="#contact" class="font-display text-2xl text-cyan-400 mobile-link">Contact</a>
        </div>
        <button class="absolute top-6 right-6 text-cyan-400" id="close-menu">
            <i data-lucide="x" class="w-8 h-8"></i>
        </button>
    </div>

    <!-- Hero Section -->
    <section id="home" class="min-h-screen flex items-center relative pt-20">
        <div class="max-w-7xl mx-auto px-6 grid md:grid-cols-2 gap-12 items-center">
            <div class="space-y-6">
                <div class="inline-block px-4 py-2 rounded-full glass-card border-cyan-500/20">
                    <span class="text-cyan-400 text-xs uppercase tracking-[0.2em]">Data Engineer & Architect</span>
                </div>
                
                <h1 class="font-display text-5xl md:text-7xl font-light leading-tight">
                    Mehul Kumar<br>
                    <span class="gradient-text font-medium">Sinha</span>
                </h1>
                
                <p class="text-gray-400 text-lg max-w-md leading-relaxed">
                    Crafting scalable data pipelines and distributed systems. 
                    Currently engineering the future at <span class="text-cyan-400">Eucloid</span>.
                </p>

                <div class="flex gap-4 pt-4">
                    <a href="#experience" class="btn-primary px-8 py-3 rounded-full hover-target inline-flex items-center gap-2">
                        View Work <i data-lucide="arrow-right" class="w-4 h-4"></i>
                    </a>
                    <a href="#contact" class="px-8 py-3 rounded-full border border-white/10 text-gray-300 hover:border-cyan-400/50 hover:text-cyan-400 transition-all hover-target">
                        Get in Touch
                    </a>
                </div>
            </div>

            <div class="relative hidden md:block">
                <div class="relative w-full aspect-square max-w-md ml-auto">
                    <div class="absolute inset-0 bg-gradient-to-br from-cyan-500/10 to-violet-500/10 rounded-2xl blur-3xl"></div>
                    <div class="relative h-full glass-card rounded-2xl p-8 flex items-center justify-center border-cyan-500/10">
                        <div class="text-center space-y-4">
                            <div class="w-32 h-32 mx-auto rounded-full bg-gradient-to-br from-cyan-500/20 to-violet-500/20 flex items-center justify-center border border-cyan-500/20">
                                <span class="font-display text-4xl text-cyan-400">MKS</span>
                            </div>
                            <div class="space-y-2">
                                <div class="flex justify-between text-xs text-gray-500 uppercase tracking-widest">
                                    <span>Status</span>
                                    <span class="text-cyan-400">Online</span>
                                </div>
                                <div class="w-full h-px bg-gradient-to-r from-transparent via-cyan-500/30 to-transparent"></div>
                                <div class="flex justify-between text-xs text-gray-500 uppercase tracking-widest">
                                    <span>Location</span>
                                    <span>India</span>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <div class="absolute bottom-10 left-1/2 transform -translate-x-1/2 animate-bounce opacity-50">
            <i data-lucide="chevron-down" class="w-5 h-5 text-cyan-400"></i>
        </div>
    </section>

    <!-- About Section -->
    <section id="about" class="py-32 relative">
        <div class="max-w-7xl mx-auto px-6">
            <div class="grid md:grid-cols-12 gap-16">
                <div class="md:col-span-4 reveal">
                    <span class="text-cyan-400 text-xs uppercase tracking-[0.2em] block mb-4">01. About</span>
                    <h2 class="font-display text-4xl md:text-5xl text-white mb-6">System<br>Architecture</h2>
                    <div class="w-16 h-px bg-gradient-to-r from-cyan-400 to-violet-400"></div>
                </div>
                
                <div class="md:col-span-8 space-y-8 reveal">
                    <div class="glass-card p-8 md:p-10 rounded-2xl">
                        <p class="text-xl text-gray-200 leading-relaxed mb-6 font-light">
                            I'm a <span class="text-cyan-400">Data Engineer</span> at Eucloid Data Solutions, 
                            specializing in the design and implementation of scalable data pipelines and 
                            distributed systems. My work bridges the gap between raw data and actionable 
                            intelligence.
                        </p>
                        <p class="text-gray-400 leading-relaxed mb-6">
                            With a foundation in Computer Science from Manipal University Jaipur and 
                            certifications in Databricks Lakehouse Platform, I bring both theoretical 
                            depth and practical expertise to complex data challenges.
                        </p>
                        <p class="text-gray-400 leading-relaxed">
                            Previously, I led web development initiatives at Aural and contributed to 
                            business strategy at Scaler. I believe in elegant solutions—systems that are 
                            not only powerful and scalable but also maintainable and intuitive.
                        </p>
                    </div>

                    <div class="grid grid-cols-3 gap-6">
                        <div class="glass-card p-6 rounded-xl text-center reveal">
                            <div class="font-display text-3xl text-cyan-400 mb-2">2+</div>
                            <div class="text-xs text-gray-500 uppercase tracking-widest">Years Experience</div>
                        </div>
                        <div class="glass-card p-6 rounded-xl text-center reveal">
                            <div class="font-display text-3xl text-violet-400 mb-2">50+</div>
                            <div class="text-xs text-gray-500 uppercase tracking-widest">Projects</div>
                        </div>
                        <div class="glass-card p-6 rounded-xl text-center reveal">
                            <div class="font-display text-3xl text-cyan-400 mb-2">5</div>
                            <div class="text-xs text-gray-500 uppercase tracking-widest">Companies</div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Experience Section -->
    <section id="experience" class="py-32 relative bg-deep-800/50">
        <div class="max-w-5xl mx-auto px-6">
            <div class="text-center mb-20 reveal">
                <span class="text-cyan-400 text-xs uppercase tracking-[0.2em] block mb-4">02. Experience</span>
                <h2 class="font-display text-4xl md:text-5xl text-white">Professional Journey</h2>
            </div>

            <div class="relative space-y-12">
                <div class="timeline-line"></div>

                <!-- Eucloid -->
                <div class="relative pl-8 md:pl-0 reveal">
                    <div class="timeline-dot"></div>
                    <div class="md:ml-12 glass-card p-8 rounded-xl hover-target cursor-pointer">
                        <div class="flex flex-col md:flex-row md:items-center justify-between mb-4">
                            <div>
                                <h3 class="font-display text-xl text-white mb-1">Data Engineer</h3>
                                <p class="text-cyan-400 text-sm">Eucloid Data Solutions</p>
                            </div>
                            <span class="text-gray-500 text-xs mt-2 md:mt-0 font-mono uppercase tracking-widest">2024 — Present</span>
                        </div>
                        <p class="text-gray-400 text-sm leading-relaxed mb-4">
                            Architecting high-throughput data pipelines using Apache Spark and Databricks. 
                            Implementing ETL workflows and optimizing data lakes for enterprise-scale systems.
                        </p>
                        <div class="flex flex-wrap gap-2">
                            <span class="skill-tag px-3 py-1 rounded-full text-xs">Databricks</span>
                            <span class="skill-tag px-3 py-1 rounded-full text-xs">Apache Spark</span>
                            <span class="skill-tag px-3 py-1 rounded-full text-xs">Python</span>
                            <span class="skill-tag px-3 py-1 rounded-full text-xs">AWS</span>
                        </div>
                    </div>
                </div>

                <!-- Scaler -->
                <div class="relative pl-8 md:pl-0 reveal">
                    <div class="timeline-dot" style="border-color: #a78bfa; box-shadow: 0 0 10px rgba(167, 139, 250, 0.5);"></div>
                    <div class="md:ml-12 glass-card p-8 rounded-xl hover-target cursor-pointer">
                        <div class="flex flex-col md:flex-row md:items-center justify-between mb-4">
                            <div>
                                <h3 class="font-display text-xl text-white mb-1">Business Development Trainee</h3>
                                <p class="text-violet-400 text-sm">Scaler</p>
                            </div>
                            <span class="text-gray-500 text-xs mt-2 md:mt-0 font-mono uppercase tracking-widest">Jan — Apr 2024</span>
                        </div>
                        <p class="text-gray-400 text-sm leading-relaxed">
                            Strategic market analysis and business development. Collaborated with cross-functional 
                            teams to drive growth metrics in the ed-tech sector.
                        </p>
                    </div>
                </div>

                <!-- Aural Deputy -->
                <div class="relative pl-8 md:pl-0 reveal">
                    <div class="timeline-dot"></div>
                    <div class="md:ml-12 glass-card p-8 rounded-xl hover-target cursor-pointer">
                        <div class="flex flex-col md:flex-row md:items-center justify-between mb-4">
                            <div>
                                <h3 class="font-display text-xl text-white mb-1">Deputy Head of Web Development</h3>
                                <p class="text-cyan-400 text-sm">Aural</p>
                            </div>
                            <span class="text-gray-500 text-xs mt-2 md:mt-0 font-mono uppercase tracking-widest">2022 — 2023</span>
                        </div>
                        <p class="text-gray-400 text-sm leading-relaxed mb-4">
                            Led development teams in building scalable web architectures. Orchestrated deployment 
                            pipelines and mentored junior developers.
                        </p>
                        <div class="flex flex-wrap gap-2">
                            <span class="skill-tag px-3 py-1 rounded-full text-xs">React.js</span>
                            <span class="skill-tag px-3 py-1 rounded-full text-xs">Node.js</span>
                            <span class="skill-tag px-3 py-1 rounded-full text-xs">Leadership</span>
                        </div>
                    </div>
                </div>

                <!-- Aural App Dev -->
                <div class="relative pl-8 md:pl-0 reveal">
                    <div class="timeline-dot" style="border-color: #a78bfa;"></div>
                    <div class="md:ml-12 glass-card p-8 rounded-xl hover-target cursor-pointer">
                        <div class="flex flex-col md:flex-row md:items-center justify-between mb-4">
                            <div>
                                <h3 class="font-display text-xl text-white mb-1">App Developer</h3>
                                <p class="text-violet-400 text-sm">Aural</p>
                            </div>
                            <span class="text-gray-500 text-xs mt-2 md:mt-0 font-mono uppercase tracking-widest">2022 — 2023</span>
                        </div>
                        <p class="text-gray-400 text-sm leading-relaxed">
                            Engineered cross-platform mobile applications using Flutter and implemented RESTful APIs 
                            with reactive state management.
                        </p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Skills Section -->
    <section id="skills" class="py-32 relative">
        <div class="max-w-7xl mx-auto px-6">
            <div class="grid md:grid-cols-2 gap-16 items-start">
                <div class="reveal">
                    <span class="text-cyan-400 text-xs uppercase tracking-[0.2em] block mb-4">03. Skills</span>
                    <h2 class="font-display text-4xl md:text-5xl text-white mb-8">Technical Proficiency</h2>
                    <p class="text-gray-400 leading-relaxed mb-8">
                        A curated toolkit of technologies and methodologies I've mastered throughout my career. 
                        Each skill represents countless hours of problem-solving and system architecture.
                    </p>
                    <div class="w-16 h-px bg-gradient-to-r from-cyan-400 to-violet-400"></div>
                </div>

                <div class="grid grid-cols-2 gap-6 reveal">
                    <div class="space-y-4">
                        <h4 class="text-cyan-400 text-xs uppercase tracking-widest mb-4">Data Engineering</h4>
                        <div class="skill-tag px-4 py-2 rounded-lg text-sm inline-block">Apache Spark</div>
                        <div class="skill-tag px-4 py-2 rounded-lg text-sm inline-block">Databricks</div>
                        <div class="skill-tag px-4 py-2 rounded-lg text-sm inline-block">ETL Pipelines</div>
                        <div class="skill-tag px-4 py-2 rounded-lg text-sm inline-block">Delta Lake</div>
                        <div class="skill-tag px-4 py-2 rounded-lg text-sm inline-block">Airflow</div>
                    </div>
                    
                    <div class="space-y-4">
                        <h4 class="text-violet-400 text-xs uppercase tracking-widest mb-4">Cloud & DevOps</h4>
                        <div class="skill-tag px-4 py-2 rounded-lg text-sm inline-block">Amazon Web Services</div>
                        <div class="skill-tag px-4 py-2 rounded-lg text-sm inline-block">Microsoft Azure</div>
                        <div class="skill-tag px-4 py-2 rounded-lg text-sm inline-block">Docker</div>
                        <div class="skill-tag px-4 py-2 rounded-lg text-sm inline-block">Kubernetes</div>
                        <div class="skill-tag px-4 py-2 rounded-lg text-sm inline-block">CI/CD</div>
                    </div>

                    <div class="space-y-4">
                        <h4 class="text-cyan-400 text-xs uppercase tracking-widest mb-4">Programming</h4>
                        <div class="skill-tag px-4 py-2 rounded-lg text-sm inline-block">Python</div>
                        <div class="skill-tag px-4 py-2 rounded-lg text-sm inline-block">SQL</div>
                        <div class="skill-tag px-4 py-2 rounded-lg text-sm inline-block">Go</div>
                        <div class="skill-tag px-4 py-2 rounded-lg text-sm inline-block">Java</div>
                    </div>

                    <div class="space-y-4">
                        <h4 class="text-violet-400 text-xs uppercase tracking-widest mb-4">Web & Mobile</h4>
                        <div class="skill-tag px-4 py-2 rounded-lg text-sm inline-block">React.js</div>
                        <div class="skill-tag px-4 py-2 rounded-lg text-sm inline-block">Node.js</div>
                        <div class="skill-tag px-4 py-2 rounded-lg text-sm inline-block">Flutter</div>
                        <div class="skill-tag px-4 py-2 rounded-lg text-sm inline-block">TypeScript</div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Certifications -->
    <section id="certifications" class="py-32 relative bg-deep-800/30">
        <div class="max-w-4xl mx-auto px-6 text-center">
            <span class="text-cyan-400 text-xs uppercase tracking-[0.2em] block mb-4 reveal">04. Certifications</span>
            <h2 class="font-display text-4xl md:text-5xl text-white mb-16 reveal">Credentials</h2>

            <div class="glass-card p-10 md:p-16 rounded-2xl reveal hover-target">
                <div class="w-20 h-20 mx-auto mb-8 rounded-full bg-cyan-500/10 flex items-center justify-center border border-cyan-500/30">
                    <i data-lucide="award" class="w-10 h-10 text-cyan-400"></i>
                </div>
                
                <h3 class="font-display text-3xl text-white mb-2">Databricks Certified</h3>
                <p class="gradient-text text-lg mb-6 font-medium">Data Engineer Associate</p>
                
                <p class="text-gray-400 max-w-2xl mx-auto mb-8 leading-relaxed">
                    Professional certification validating expertise in designing, building, and maintaining 
                    data pipelines using the Databricks Lakehouse Platform, including Delta Lake and Apache Spark.
                </p>
                
                <a href="https://credentials.databricks.com/947fcbc1-ffa3-42e0-ae9f-50c213b10a9d" 
                   target="_blank"
                   class="inline-flex items-center gap-2 text-cyan-400 hover:text-white transition-colors text-sm uppercase tracking-widest border-b border-cyan-400/30 pb-1 hover:border-cyan-400 hover-target">
                    Verify Credential <i data-lucide="external-link" class="w-4 h-4"></i>
                </a>
            </div>

            <div class="grid md:grid-cols-2 gap-6 mt-8">
                <div class="glass-card p-8 rounded-xl reveal text-left hover-target">
                    <p class="text-cyan-400 text-xs uppercase tracking-widest mb-2">Education</p>
                    <h4 class="font-display text-xl text-white">B.Tech Computer Science</h4>
                    <p class="text-gray-500 text-sm mt-1">Manipal University Jaipur</p>
                </div>
                <div class="glass-card p-8 rounded-xl reveal text-left hover-target">
                    <p class="text-violet-400 text-xs uppercase tracking-widest mb-2">Earlier</p>
                    <h4 class="font-display text-xl text-white">High School Diploma</h4>
                    <p class="text-gray-500 text-sm mt-1">Delhi Public School</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="py-32 relative">
        <div class="max-w-3xl mx-auto px-6 text-center">
            <span class="text-cyan-400 text-xs uppercase tracking-[0.2em] block mb-4 reveal">05. Contact</span>
            <h2 class="font-display text-4xl md:text-6xl text-white mb-6 reveal">Let's Connect</h2>
            <p class="text-gray-400 mb-12 reveal">
                I'm currently open to new opportunities and collaborations. 
                Whether you have a question or just want to say hi, I'll try my best to get back to you.
            </p>

            <div class="glass-card p-8 md:p-12 rounded-2xl reveal">
                <form class="space-y-6 text-left" id="contact-form">
                    <div class="grid md:grid-cols-2 gap-6">
                        <div>
                            <label class="block text-xs uppercase tracking-widest text-gray-500 mb-2">Name</label>
                            <input type="text" required
                                class="w-full bg-deep-900/50 border border-white/10 rounded-lg px-4 py-3 text-white focus:outline-none focus:border-cyan-400/50 transition-colors hover-target"
                                placeholder="John Doe">
                        </div>
                        <div>
                            <label class="block text-xs uppercase tracking-widest text-gray-500 mb-2">Email</label>
                            <input type="email" required
                                class="w-full bg-deep-900/50 border border-white/10 rounded-lg px-4 py-3 text-white focus:outline-none focus:border-cyan-400/50 transition-colors hover-target"
                                placeholder="john@example.com">
                        </div>
                    </div>
                    <div>
                        <label class="block text-xs uppercase tracking-widest text-gray-500 mb-2">Subject</label>
                        <input type="text" required
                            class="w-full bg-deep-900/50 border border-white/10 rounded-lg px-4 py-3 text-white focus:outline-none focus:border-cyan-400/50 transition-colors hover-target"
                            placeholder="Project Collaboration">
                    </div>
                    <div>
                        <label class="block text-xs uppercase tracking-widest text-gray-500 mb-2">Message</label>
                        <textarea rows="5" required
                            class="w-full bg-deep-900/50 border border-white/10 rounded-lg px-4 py-3 text-white focus:outline-none focus:border-cyan-400/50 transition-colors resize-none hover-target"
                            placeholder="Tell me about your project..."></textarea>
                    </div>
                    <button type="submit" 
                        class="w-full py-4 bg-cyan-500/10 border border-cyan-400/30 text-cyan-400 hover:bg-cyan-400 hover:text-deep-900 transition-all duration-300 uppercase tracking-widest text-sm font-medium rounded-lg hover-target">
                        Send Message
                    </button>
                </form>
            </div>

            <div class="flex justify-center gap-8 mt-12 reveal">
                <a href="https://linkedin.com/in/mehul-kumar-sinha" target="_blank" class="text-gray-500 hover:text-cyan-400 transition-colors hover-target">
                    <i data-lucide="linkedin" class="w-6 h-6"></i>
                </a>
                <a href="#" class="text-gray-500 hover:text-cyan-400 transition-colors hover-target">
                    <i data-lucide="github" class="w-6 h-6"></i>
                </a>
                <a href="#" class="text-gray-500 hover:text-cyan-400 transition-colors hover-target">
                    <i data-lucide="twitter" class="w-6 h-6"></i>
                </a>
                <a href="mailto:contact@example.com" class="text-gray-500 hover:text-cyan-400 transition-colors hover-target">
                    <i data-lucide="mail" class="w-6 h-6"></i>
                </a>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="py-8 border-t border-white/5 bg-deep-900">
        <div class="max-w-7xl mx-auto px-6 flex flex-col md:flex-row justify-between items-center gap-4">
            <div class="font-display text-cyan-400 text-xl tracking-widest">MKS</div>
            <div class="text-gray-600 text-sm">
                Designed & Built with precision
            </div>
            <div class="text-gray-600 text-sm">
                © 2026 Mehul Kumar Sinha
            </div>
        </div>
    </footer>

    <script>
        // Initialize Icons
        lucide.createIcons();

        // Loading Animation
        const loader = document.getElementById('loader');
        const progress = document.getElementById('loader-progress');
        let loadProgress = 0;
        
        const loadInterval = setInterval(() => {
            loadProgress += Math.random() * 30;
            if (loadProgress >= 100) {
                loadProgress = 100;
                clearInterval(loadInterval);
                setTimeout(() => {
                    loader.classList.add('hidden');
                }, 500);
            }
            progress.style.width = loadProgress + '%';
        }, 200);

        // Custom Cursor
        const cursorDot = document.getElementById('cursor-dot');
        const cursorOutline = document.getElementById('cursor-outline');
        const hoverTargets = document.querySelectorAll('.hover-target');

        window.addEventListener('mousemove', (e) => {
            const posX = e.clientX;
            const posY = e.clientY;

            cursorDot.style.left = `${posX}px`;
            cursorDot.style.top = `${posY}px`;

            cursorOutline.animate({
                left: `${posX}px`,
                top: `${posY}px`
            }, { duration: 500, fill: "forwards" });
        });

        hoverTargets.forEach(target => {
            target.addEventListener('mouseenter', () => {
                cursorOutline.classList.add('hover');
            });
            target.addEventListener('mouseleave', () => {
                cursorOutline.classList.remove('hover');
            });
        });

        // Audio Control
        const audioControl = document.getElementById('audio-control');
        const ambientAudio = document.getElementById('ambient-audio');
        const audioIcon = document.getElementById('audio-icon');
        let isPlaying = false;

        audioControl.addEventListener('click', () => {
            if (isPlaying) {
                ambientAudio.pause();
                audioControl.classList.remove('playing');
                audioIcon.setAttribute('data-lucide', 'volume-x');
            } else {
                ambientAudio.volume = 0.2;
                ambientAudio.play().catch(e => console.log('Audio play failed'));
                audioControl.classList.add('playing');
                audioIcon.setAttribute('data-lucide', 'volume-2');
            }
            lucide.createIcons();
            isPlaying = !isPlaying;
        });

        // Navigation Scroll Effect
        const navbar = document.getElementById('navbar');
        window.addEventListener('scroll', () => {
            if (window.scrollY > 50) {
                navbar.classList.add('nav-glass');
            } else {
                navbar.classList.remove('nav-glass');
            }
        });

        // Scroll Progress
        const progressBar = document.getElementById('progress-bar');
        window.addEventListener('scroll', () => {
            const scrollTop = document.documentElement.scrollTop || document.body.scrollTop;
            const scrollHeight = document.documentElement.scrollHeight - document.documentElement.clientHeight;
            const scrolled = (scrollTop / scrollHeight) * 100;
            progressBar.style.width = scrolled + "%";
        });

        // Mobile Menu
        const mobileMenuBtn = document.getElementById('mobile-menu-btn');
        const closeMenuBtn = document.getElementById('close-menu');
        const mobileMenu = document.getElementById('mobile-menu');
        const mobileLinks = document.querySelectorAll('.mobile-link');

        mobileMenuBtn.addEventListener('click', () => {
            mobileMenu.style.transform = 'translateX(0)';
        });

        closeMenuBtn.addEventListener('click', () => {
            mobileMenu.style.transform = 'translateX(100%)';
        });

        mobileLinks.forEach(link => {
            link.addEventListener('click', () => {
                mobileMenu.style.transform = 'translateX(100%)';
            });
        });

        // GSAP Animations
        gsap.registerPlugin(ScrollTrigger);

        // Reveal animations
        const reveals = document.querySelectorAll('.reveal');
        reveals.forEach((element, i) => {
            gsap.fromTo(element, 
                {
                    opacity: 0,
                    y: 30
                },
                {
                    opacity: 1,
                    y: 0,
                    duration: 0.8,
                    ease: "power2.out",
                    scrollTrigger: {
                        trigger: element,
                        start: "top 85%",
                        toggleActions: "play none none reverse"
                    },
                    delay: i * 0.1
                }
            );
        });

        // Smooth scroll
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });

        // Form submission
        document.getElementById('contact-form').addEventListener('submit', (e) => {
            e.preventDefault();
            const btn = e.target.querySelector('button');
            const originalText = btn.textContent;
            
            btn.textContent = 'Sending...';
            btn.disabled = true;
            
            setTimeout(() => {
                btn.textContent = 'Message Sent';
                btn.classList.add('bg-cyan-400', 'text-deep-900');
                
                setTimeout(() => {
                    btn.textContent = originalText;
                    btn.disabled = false;
                    btn.classList.remove('bg-cyan-400', 'text-deep-900');
                    e.target.reset();
                }, 3000);
            }, 1500);
        });
    </script>
</body>
</html>
