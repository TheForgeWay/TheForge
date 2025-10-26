<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>The Forge - Transform Everything</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=EB+Garamond:wght@400;500;600;700&family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        body {
            box-sizing: border-box;
        }
        
        .garamond {
            font-family: 'EB Garamond', serif;
        }
        
        .inter {
            font-family: 'Inter', sans-serif;
        }
        
        .hero-section {
            background: linear-gradient(135deg, #000000 0%, #1a1a1a 100%);
            min-height: 100vh;
        }
        
        .fade-in {
            animation: fadeIn 0.8s ease-out;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(30px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        .slide-in {
            animation: slideIn 0.6s ease-out;
        }
        
        @keyframes slideIn {
            from { opacity: 0; transform: translateX(-30px); }
            to { opacity: 1; transform: translateX(0); }
        }
        
        .mobile-menu {
            transform: translateX(-100%);
            transition: transform 0.3s ease-in-out;
        }
        
        .mobile-menu.open {
            transform: translateX(0);
        }
        
        .btn-primary {
            background: linear-gradient(135deg, #000000 0%, #333333 100%);
            transition: all 0.3s ease;
        }
        
        .btn-primary:hover {
            background: linear-gradient(135deg, #333333 0%, #555555 100%);
            transform: translateY(-2px);
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.3);
        }
        
        .section-bg-light {
            background: linear-gradient(135deg, #ffffff 0%, #f8f9fa 100%);
        }
        
        .section-bg-accent {
            background: linear-gradient(135deg, #628ca2 0%, #4a6b7a 100%);
        }
        
        .text-shadow {
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
        }
        
        .logo-tf {
            font-weight: 700;
            letter-spacing: -2px;
        }
    </style>
</head>
<body class="inter bg-white">
    <!-- Mobile Menu Overlay -->
    <div id="mobileMenu" class="mobile-menu fixed inset-y-0 left-0 z-50 w-64 bg-black text-white">
        <div class="p-6">
            <div class="flex justify-between items-center mb-8">
                <h2 class="garamond text-2xl font-bold">THE FORGE</h2>
                <button onclick="toggleMobileMenu()" class="text-white hover:text-gray-300">
                    <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"></path>
                    </svg>
                </button>
            </div>
            <nav class="space-y-4">
                <a href="#home" onclick="showPage('home'); toggleMobileMenu()" class="block py-3 px-4 hover:bg-gray-800 rounded transition-colors">Home</a>
                <a href="#about" onclick="showPage('about'); toggleMobileMenu()" class="block py-3 px-4 hover:bg-gray-800 rounded transition-colors">About Book</a>
                <a href="#order" onclick="showPage('order'); toggleMobileMenu()" class="block py-3 px-4 hover:bg-gray-800 rounded transition-colors">Order The Book</a>
                <a href="#contact" onclick="showPage('contact'); toggleMobileMenu()" class="block py-3 px-4 hover:bg-gray-800 rounded transition-colors">Contact</a>
                <a href="#mentorship" onclick="showPage('mentorship'); toggleMobileMenu()" class="block py-3 px-4 hover:bg-gray-800 rounded transition-colors">Mentorship</a>
                <a href="#community" onclick="showPage('community'); toggleMobileMenu()" class="block py-3 px-4 hover:bg-gray-800 rounded transition-colors">Join Community</a>
            </nav>
        </div>
    </div>

    <!-- Header -->
    <header class="fixed top-0 left-0 right-0 z-40 bg-white/95 backdrop-blur-sm border-b border-gray-200">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex justify-between items-center h-16">
                <!-- Mobile Menu Button -->
                <button onclick="toggleMobileMenu()" class="lg:hidden p-2 rounded-md hover:bg-gray-100">
                    <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"></path>
                    </svg>
                </button>

                <!-- Logo -->
                <div class="flex items-center space-x-3">
                    <div class="garamond logo-tf text-3xl text-black">TF</div>
                    <h1 class="garamond text-2xl font-bold text-black">THE FORGE</h1>
                </div>

                <!-- Desktop Navigation -->
                <nav class="hidden lg:flex space-x-8">
                    <a href="#home" onclick="showPage('home')" class="text-gray-700 hover:text-black px-3 py-2 font-medium transition-colors">Home</a>
                    <a href="#about" onclick="showPage('about')" class="text-gray-700 hover:text-black px-3 py-2 font-medium transition-colors">About Book</a>
                    <a href="#order" onclick="showPage('order')" class="text-gray-700 hover:text-black px-3 py-2 font-medium transition-colors">Order The Book</a>
                    <a href="#contact" onclick="showPage('contact')" class="text-gray-700 hover:text-black px-3 py-2 font-medium transition-colors">Contact</a>
                    <a href="#mentorship" onclick="showPage('mentorship')" class="text-gray-700 hover:text-black px-3 py-2 font-medium transition-colors">Mentorship</a>
                    <a href="#community" onclick="showPage('community')" class="text-gray-700 hover:text-black px-3 py-2 font-medium transition-colors">Join Community</a>
                </nav>
            </div>
        </div>
    </header>

    <!-- Main Content -->
    <main>
        <!-- Home Page -->
        <div id="homePage" class="page">
            <!-- Hero Section -->
            <section class="hero-section flex items-center justify-center text-center text-white px-4">
                <div class="max-w-4xl mx-auto fade-in">
                    <h1 class="garamond text-6xl md:text-8xl font-bold mb-6 text-shadow leading-tight">
                        Stop Waiting.<br>
                        Start Winning.<br>
                        <span class="text-gray-300">Transform Everything.</span>
                    </h1>
                    <p class="inter text-xl md:text-2xl mb-12 text-gray-300 font-light">
                        With The Forge, ordinary ends… and greatness begins.
                    </p>
                    <button onclick="showPage('order')" class="btn-primary text-white px-12 py-4 text-lg font-semibold rounded-lg inter">
                        Start the 100 Days War
                    </button>
                </div>
            </section>

            <!-- Main Content Section -->
            <section class="section-bg-light py-20 px-4">
                <div class="max-w-4xl mx-auto">
                    <div class="text-center mb-16 slide-in">
                        <p class="inter text-2xl md:text-3xl text-gray-800 leading-relaxed mb-8">
                            You said you'd change. <strong>You didn't.</strong><br>
                            You waited for motivation. <strong>It never came.</strong><br>
                            You let fear steal another year of your life.
                        </p>
                        <p class="inter text-xl text-gray-700 mb-8">
                            The Forge isn't another motivational book — it's your mirror, your battlefield, your rebirth.
                        </p>
                        
                        <!-- Promotional Image -->
                        <div class="text-center mb-12">
                            <img src="https://www.dropbox.com/scl/fi/llr1r7z7u8ui91bwv90dy/. .png?rlkey=u421zqpi28a4fma5thoo092l9&st=zdcrdfz5&dl=1" alt="The Forge Transformation" class="mx-auto max-w-full h-auto rounded-lg shadow-xl" onerror="this.src=''; this.alt='Image failed to load'; this.style.display='none';">
                        </div>
                    </div>

                    <div class="grid md:grid-cols-2 gap-12 mb-16">
                        <div class="fade-in">
                            <h3 class="garamond text-3xl font-bold text-black mb-6">In 100 days, you'll master:</h3>
                            <ul class="inter text-lg text-gray-700 space-y-3">
                                <li class="flex items-center"><span class="w-2 h-2 bg-black rounded-full mr-4"></span>Ruthless discipline</li>
                                <li class="flex items-center"><span class="w-2 h-2 bg-black rounded-full mr-4"></span>Relentless focus</li>
                                <li class="flex items-center"><span class="w-2 h-2 bg-black rounded-full mr-4"></span>Control under chaos</li>
                                <li class="flex items-center"><span class="w-2 h-2 bg-black rounded-full mr-4"></span>The mindset that makes weakness impossible</li>
                            </ul>
                            <p class="inter text-lg text-black font-semibold mt-6">
                                You won't read this book — you'll live it.
                            </p>
                        </div>

                        <div class="fade-in">
                            <h3 class="garamond text-3xl font-bold text-black mb-6">In The Forge:</h3>
                            <ul class="inter text-lg text-gray-700 space-y-3">
                                <li class="flex items-center"><span class="w-2 h-2 bg-black rounded-full mr-4"></span>100 structured lessons</li>
                                <li class="flex items-center"><span class="w-2 h-2 bg-black rounded-full mr-4"></span>Daily checklists & reflection questions</li>
                                <li class="flex items-center"><span class="w-2 h-2 bg-black rounded-full mr-4"></span>"Break & Replace" method</li>
                                <li class="flex items-center"><span class="w-2 h-2 bg-black rounded-full mr-4"></span>10-day tactical reviews</li>
                                <li class="flex items-center"><span class="w-2 h-2 bg-black rounded-full mr-4"></span>Case Study</li>
                                <li class="flex items-center"><span class="w-2 h-2 bg-black rounded-full mr-4"></span>Victory Log to track real growth</li>
                                <li class="flex items-center"><span class="w-2 h-2 bg-black rounded-full mr-4"></span>And more</li>
                            </ul>
                        </div>
                    </div>

                    <div class="text-center mb-16">
                        <p class="garamond text-2xl text-black font-semibold mb-8">
                            This isn't a book you finish. It's a version of yourself you meet.
                        </p>
                        <h2 class="garamond text-4xl font-bold text-black mb-6">Begin Your 100-Day Transformation</h2>
                        <p class="inter text-lg text-gray-700 mb-8">
                            Order your physical edition now and gain exclusive access to The Forge Community — a space built for growth, action, and accountability.
                        </p>
                        <button onclick="showPage('order')" class="btn-primary text-white px-10 py-4 text-lg font-semibold rounded-lg inter">
                            I'm Ready to Rise
                        </button>
                    </div>
                </div>
            </section>

            <!-- Why This Book Exists Section -->
            <section class="bg-gray-100 py-20 px-4">
                <div class="max-w-4xl mx-auto">
                    <div class="text-center mb-16">
                        <h2 class="garamond text-5xl font-bold text-black mb-8">Why This Book Exists</h2>
                        <p class="inter text-xl text-gray-700 leading-relaxed mb-8">
                            The Forge was not written to motivate you — it was created to rebuild you.
                        </p>
                        <p class="inter text-lg text-gray-700 leading-relaxed mb-8">
                            In a culture obsessed with shortcuts and comfort, this book is a rebellion.
                        </p>
                        <p class="inter text-lg text-gray-700 leading-relaxed mb-8">
                            It exists to restore the discipline, identity, and mental toughness that modern life has erased.
                        </p>
                        <p class="inter text-lg text-black font-semibold">
                            Each page is a strike of the hammer — shaping your mind, not soothing it.
                        </p>
                    </div>

                    <div class="grid md:grid-cols-3 gap-12 mb-16">
                        <div class="text-center fade-in">
                            <h3 class="garamond text-3xl font-bold text-black mb-6">The Core Idea</h3>
                            <p class="inter text-gray-700 leading-relaxed mb-4">
                                Real growth doesn't come from inspiration — it comes from structure.
                            </p>
                            <p class="inter text-gray-700 leading-relaxed mb-4">
                                That's why The Forge is built as a 100-day journey.
                            </p>
                            <p class="inter text-gray-700 leading-relaxed mb-4">
                                Every lesson adds a new layer to your mindset — one day, one truth, one transformation at a time.
                            </p>
                            <p class="inter text-black font-semibold">
                                By the end, you don't just think differently — you are different.
                            </p>
                        </div>

                        <div class="text-center fade-in">
                            <h3 class="garamond text-3xl font-bold text-black mb-6">Why It's Different</h3>
                            <p class="inter text-gray-700 leading-relaxed mb-4">
                                Most books tell you what to do. The Forge teaches you who to become.
                            </p>
                            <p class="inter text-gray-700 leading-relaxed mb-4">
                                It blends psychology, philosophy, and lived experience — not theories, but tools forged in real struggle.
                            </p>
                            <p class="inter text-gray-700 leading-relaxed mb-4">
                                Its tone is raw, dark, and unapologetically honest. No clichés. No sugarcoating.
                            </p>
                            <p class="inter text-black font-semibold">
                                It's not about feeling better; it's about becoming unbreakable.
                            </p>
                        </div>

                        <div class="text-center fade-in">
                            <h3 class="garamond text-3xl font-bold text-black mb-6">What You'll Gain</h3>
                            <ul class="inter text-gray-700 space-y-3 text-left">
                                <li>• A disciplined mind that no longer depends on motivation.</li>
                                <li>• The ability to turn chaos into control.</li>
                                <li>• A mindset that transforms pain into clarity.</li>
                                <li>• The strength to rebuild your identity — from the inside out.</li>
                            </ul>
                        </div>
                    </div>

                    <div class="text-center mb-16">
                        <h3 class="garamond text-4xl font-bold text-black mb-8">For Whom It Was Written</h3>
                        <div class="inter text-lg text-gray-700 space-y-4 max-w-2xl mx-auto">
                            <p>• For those who have fallen and want to rise sharper.</p>
                            <p>• For those tired of noise and ready for truth.</p>
                            <p>• For anyone who knows that greatness is not found — it's forged.</p>
                        </div>
                        <div class="mt-12">
                            <button onclick="showPage('about')" class="btn-primary text-white px-10 py-4 text-lg font-semibold rounded-lg inter">
                                More About The Book
                            </button>
                        </div>
                    </div>
                </div>
            </section>

            <!-- Book Section -->
            <section class="bg-white py-20 px-4">
                <div class="max-w-6xl mx-auto">
                    <div class="text-center mb-16">
                        <h2 class="garamond text-6xl font-bold text-black mb-8">Book</h2>
                    </div>

                    <div class="grid md:grid-cols-2 gap-12 mb-20">
                        <!-- Physical Edition -->
                        <div class="text-center">
                            <h3 class="garamond text-4xl font-bold text-black mb-2">Physical Edition</h3>
                            <p class="inter text-xl text-gray-600 mb-8">Hardcover • 259 pages</p>
                            
                            <!-- Book Image -->
                            <div class="mx-auto mb-8 w-64 h-80">
                                <img src="https://www.dropbox.com/scl/fi/5t824md15pigb06rpehfe/. .png?rlkey=uoz158v68vkrl5bui2wcmbc33&st=2vgli6fe&dl=1" alt="The Forge Physical Edition" class="w-full h-full object-cover rounded-lg shadow-2xl" onerror="this.src=''; this.alt='Image failed to load'; this.style.display='none';">
                            </div>

                            <div class="text-left max-w-md mx-auto">
                                <p class="inter text-gray-700 mb-4">
                                    Hold The Forge in your hands — a matte black hardcover designed to feel as powerful as its message.
                                </p>
                                <p class="inter text-gray-700 mb-4">
                                    The physical edition isn't just a book; it's a symbol of commitment.
                                </p>
                                <p class="inter text-gray-700 mb-2"><strong>Includes:</strong> Premium matte hardcover, 259 pages of lessons + writing sections</p>
                                <p class="inter text-gray-700 mb-2"><strong>Purpose:</strong> Built for readers who want to apply every lesson in real time</p>
                                <p class="inter text-gray-700 mb-2"><strong>Shipping:</strong> Available for Iranian</p>
                                <p class="inter text-sm text-gray-500">(Coming soon for other countries)</p>
                            </div>
                        </div>

                        <!-- Digital Edition -->
                        <div class="text-center">
                            <h3 class="garamond text-4xl font-bold text-black mb-2">Digital Edition</h3>
                            <p class="inter text-xl text-gray-600 mb-8">Full PDF • 259 pages</p>
                            
                            <!-- Book Image -->
                            <div class="mx-auto mb-8 w-64 h-80 relative">
                                <img src="https://www.dropbox.com/scl/fi/5t824md15pigb06rpehfe/. .png?rlkey=uoz158v68vkrl5bui2wcmbc33&st=2vgli6fe&dl=1" alt="The Forge Physical Edition" class="w-full h-full object-cover rounded-lg shadow-2xl" onerror="this.src=''; this.alt='Image failed to load'; this.style.display='none';">
                            </div>

                            <div class="text-left max-w-md mx-auto">
                                <p class="inter text-gray-700 mb-4">
                                    Hold The Forge in your hands — a matte black hardcover designed to feel as powerful as its message.
                                </p>
                                <p class="inter text-gray-700 mb-4">
                                    The physical edition isn't just a book; it's a symbol of commitment.
                                </p>
                                <p class="inter text-gray-700 mb-2"><strong>Includes:</strong> Premium matte hardcover, 259 pages of lessons + writing sections</p>
                                <p class="inter text-gray-700 mb-2"><strong>Purpose:</strong> Built for readers who want to apply every lesson in real time</p>
                                <p class="inter text-gray-700 mb-2"><strong>Shipping:</strong> Available for Iranian</p>
                                <p class="inter text-sm text-gray-500">(Coming soon for other countries)</p>
                            </div>
                        </div>

                        <!-- Digital Edition -->
                        <div class="text-center">
                            <h3 class="garamond text-4xl font-bold text-black mb-2">Digital Edition</h3>
                            <p class="inter text-xl text-gray-600 mb-8">Full PDF • 259 pages</p>
                            
                            <!-- Book Image -->
                            <div class="mx-auto mb-8 w-64 h-80 relative">
                                <img src="https://www.dropbox.com/scl/fi/yly4b68yx8fxxx92r4v52/file_000000007d7c6246b3744916f1c2442f.png?rlkey=hzhx9bw6gf6om1sg1b97fjskk&st=bk6sgvci&dl=1" alt="The Forge Digital Edition" class="w-full h-full object-cover rounded-lg shadow-2xl" onerror="this.src=''; this.alt='Image failed to load'; this.style.display='none';">
                                <div class="absolute top-4 right-4 bg-blue-600 text-white px-2 py-1 rounded text-xs">PDF</div>
                            </div>

                            <div class="text-left max-w-md mx-auto">
                                <p class="inter text-gray-700 mb-4">
                                    For those who want immediate access and flexibility.
                                </p>
                                <p class="inter text-gray-700 mb-4">
                                    The digital edition contains the full content of The Forge — all 100 lessons, perfectly formatted for mobile, tablet, or laptop.
                                </p>
                                <p class="inter text-gray-700 mb-4">
                                    It delivers the same intensity and clarity — but without the physical writing experience of the workbook.
                                </p>
                                <p class="inter text-gray-700 mb-2"><strong>Format:</strong> Full PDF (259 Pages)</p>
                                <p class="inter text-gray-700 mb-2"><strong>Access:</strong> Instant download after purchase</p>
                                <p class="inter text-gray-700"><strong>Ideal for:</strong> Readers who prefer digital reading and self-paced reflection</p>
                            </div>
                        </div>
                    </div>
                </div>
            </section>

            <!-- Get In Touch Section -->
            <section class="section-bg-accent py-20 px-4 text-white">
                <div class="max-w-4xl mx-auto">
                    <div class="text-center mb-12">
                        <div class="flex items-center justify-center space-x-3 mb-6">
                            <div class="garamond logo-tf text-4xl text-white">TF</div>
                            <h2 class="garamond text-4xl font-bold text-white">THE FORGE</h2>
                        </div>
                        <h3 class="garamond text-3xl font-bold text-white mb-6">Get In Touch</h3>
                        <p class="inter text-xl text-gray-100 mb-8">
                            Questions? Problems? Let's crush them — with clarity, power, and a smile.
                        </p>
                    </div>

                    <div class="flex flex-col md:flex-row justify-center items-center space-y-6 md:space-y-0 md:space-x-12">
                        <a href="https://t.me/TheForgeWay" target="_blank" rel="noopener noreferrer" class="flex items-center space-x-3 text-white hover:text-gray-200 transition-colors">
                            <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 24 24">
                                <path d="M12 0C5.374 0 0 5.373 0 12s5.374 12 12 12 12-5.373 12-12S18.626 0 12 0zm5.568 8.16c-.169 1.858-.896 6.728-.896 6.728-.377 2.618-1.407 3.071-2.896 1.904l-3.2-2.309-1.534 1.378c-.18.18-.333.333-.686.333l.231-3.289 6.046-5.412c.272-.24-.054-.384-.422-.144L8.289 13.664l-3.26-1.027c-.707-.222-.72-.707.151-.045L18.818 7.63c.592-.222 1.107.144.75 1.53z"/>
                            </svg>
                            <span class="inter text-lg">Tel: @TheForgeWay</span>
                        </a>

                        <a href="mailto:theforgebook@gmail.com" class="flex items-center space-x-3 text-white hover:text-gray-200 transition-colors">
                            <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 24 24">
                                <path d="M12 12.713l-11.985-9.713h23.97l-11.985 9.713zm0 2.574l-12-9.725v15.438h24v-15.438l-12 9.725z"/>
                            </svg>
                            <span class="inter text-lg">Email: theforgebook@gmail.com</span>
                        </a>

                        <a href="https://instagram.com/theforgeway" target="_blank" rel="noopener noreferrer" class="flex items-center space-x-3 text-white hover:text-gray-200 transition-colors">
                            <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 24 24">
                                <path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z"/>
                            </svg>
                            <span class="inter text-lg">Instagram: theforgeway</span>
                        </a>
                    </div>
                </div>
            </section>

            <!-- Inspiration Section -->
            <section class="bg-black py-20 px-4 text-white">
                <div class="max-w-4xl mx-auto text-center">
                    <p class="inter text-xl mb-8 text-gray-100">
                        Inspired by principles proven by the world's most relentless minds —
                    </p>
                    <p class="garamond text-2xl font-semibold mb-8">
                        Elon Musk, Muhammad Ali, David Goggins, Steve Jobs, Darren Hardy, Jim Rohn, Tony Robbins, Brian Tracy and many others.
                    </p>
                    <div class="border-t border-white/30 pt-8">
                        <p class="inter text-lg text-gray-100">
                            Written by <strong>Mehran Esmaeilpouri</strong>, creator of "The Forge" — a 100-day blueprint to rebuild your mind and habits from the ground up.
                        </p>
                    </div>
                </div>
            </section>

            <!-- Footer -->
            <footer class="bg-gray-900 py-8 px-4">
                <div class="max-w-4xl mx-auto text-center">
                    <p class="inter text-gray-400">© 2025 The Forge. All rights reserved.</p>
                </div>
            </footer>
        </div>

        <!-- About Book Page -->
        <div id="aboutPage" class="page hidden">
            <section class="pt-24 pb-20 px-4 bg-white">
                <div class="max-w-4xl mx-auto">
                    <div class="text-center mb-16">
                        <h1 class="garamond text-6xl font-bold text-black mb-8">About The Book</h1>
                        <h2 class="garamond text-3xl font-semibold text-gray-700 mb-12">The Forge: 100 Days, 100 Lessons, One Transformed Life</h2>
                    </div>

                    <div class="prose prose-lg max-w-none inter text-gray-700 leading-relaxed">
                        <p class="text-xl mb-8">
                            The Forge is a <strong>practical, action-oriented guide</strong> for anyone ready to transform their life. Over 100 days, it delivers 100 clear lessons designed not just to inspire, but to <strong>guide you step by step toward personal growth, mindset mastery, and unstoppable action.</strong>
                        </p>

                        <p class="mb-8">
                            Each lesson encourages readers to understand, reflect, and apply strategies that lead to <strong>real-life results.</strong> The book emphasizes <strong>practice over theory,</strong> with a dedicated workbook section where you can write down your actions, track progress, and internalize what you learn. This ensures that your transformation is not just conceptual, but <strong>tangible and lasting.</strong>
                        </p>

                        <p class="mb-8">
                            The Forge covers essential areas for personal and professional success, including:
                        </p>

                        <div class="grid md:grid-cols-2 gap-8 mb-12">
                            <div class="space-y-4">
                                <div class="flex items-start space-x-3">
                                    <div class="w-2 h-2 bg-black rounded-full mt-3 flex-shrink-0"></div>
                                    <div>
                                        <h3 class="font-semibold text-black mb-2">Mindset and self-discipline:</h3>
                                        <p>Building mental resilience to overcome challenges</p>
                                    </div>
                                </div>
                                
                                <div class="flex items-start space-x-3">
                                    <div class="w-2 h-2 bg-black rounded-full mt-3 flex-shrink-0"></div>
                                    <div>
                                        <h3 class="font-semibold text-black mb-2">Goal setting and productivity:</h3>
                                        <p>Turning intentions into concrete daily actions</p>
                                    </div>
                                </div>
                            </div>

                            <div class="space-y-4">
                                <div class="flex items-start space-x-3">
                                    <div class="w-2 h-2 bg-black rounded-full mt-3 flex-shrink-0"></div>
                                    <div>
                                        <h3 class="font-semibold text-black mb-2">Habits and routines:</h3>
                                        <p>Developing consistent behaviors that compound over time</p>
                                    </div>
                                </div>
                                
                                <div class="flex items-start space-x-3">
                                    <div class="w-2 h-2 bg-black rounded-full mt-3 flex-shrink-0"></div>
                                    <div>
                                        <h3 class="font-semibold text-black mb-2">Self-awareness and reflection:</h3>
                                        <p>Learning from experience and making deliberate choices</p>
                                    </div>
                                </div>
                            </div>
                        </div>

                        <p class="mb-8">
                            What makes The Forge unique is its <strong>actionable, daily structure.</strong> Readers don't just read—they <strong>engage, practice, and track their progress,</strong> turning lessons into habits and ideas into results. Whether you aim to boost focus, achieve ambitious goals, or unlock hidden potential, this book serves as a <strong>daily guide, mentor, and accountability partner.</strong>
                        </p>

                        <p class="text-xl font-semibold text-black text-center bg-gray-50 p-8 rounded-lg">
                            By the end, you'll have built the <strong>mindset, skills, and habits</strong> to confidently face challenges and create lasting change. The Forge is more than a book—it's a <strong>transformational journey to becoming unstoppable.</strong>
                        </p>
                    </div>

                    <div class="text-center mt-16">
                        <button onclick="showPage('order')" class="btn-primary text-white px-10 py-4 text-lg font-semibold rounded-lg inter">
                            Get Your Copy Now
                        </button>
                    </div>
                </div>
            </section>
        </div>

        <!-- Order Page -->
        <div id="orderPage" class="page hidden">
            <section class="pt-24 pb-20 px-4 bg-white">
                <div class="max-w-6xl mx-auto">
                    <div class="text-center mb-16">
                        <h1 class="garamond text-6xl font-bold text-black mb-8">Order Your Book</h1>
                    </div>

                    <div class="grid md:grid-cols-2 gap-12 mb-20">
                        <!-- Physical Edition -->
                        <div class="text-center">
                            <h3 class="garamond text-4xl font-bold text-black mb-2">Physical Edition</h3>
                            <p class="inter text-xl text-gray-600 mb-8">Hardcover • 259 pages</p>
                            
                            <!-- Book Image -->
                            <div class="mx-auto mb-8 w-64 h-80">
                                <img src="https://www.dropbox.com/scl/fi/5t824md15pigb06rpehfe/. .png?rlkey=uoz158v68vkrl5bui2wcmbc33&st=2vgli6fe&dl=1" alt="The Forge Physical Edition" class="w-full h-full object-cover rounded-lg shadow-2xl" onerror="this.src=''; this.alt='Image failed to load'; this.style.display='none';">
                            </div>

                            <div class="text-left max-w-md mx-auto mb-8">
                                <p class="inter text-gray-700 mb-4">
                                    Hold The Forge in your hands — a matte black hardcover designed to feel as powerful as its message.
                                </p>
                                <p class="inter text-gray-700 mb-4">
                                    The physical edition isn't just a book; it's a symbol of commitment.
                                </p>
                                <p class="inter text-gray-700 mb-2"><strong>Includes:</strong> Premium matte hardcover, 259 pages of lessons + writing sections</p>
                                <p class="inter text-gray-700 mb-2"><strong>Purpose:</strong> Built for readers who want to apply every lesson in real time</p>
                                <p class="inter text-gray-700 mb-2"><strong>Shipping:</strong> Available for Iranian</p>
                                <p class="inter text-sm text-gray-500">(Coming soon for other countries)</p>
                            </div>

                            <button onclick="showOrderForm('physical')" class="btn-primary text-white px-8 py-3 text-lg font-semibold rounded-lg inter w-full max-w-md">
                                Get Your Book
                            </button>
                        </div>

                        <!-- Digital Edition -->
                        <div class="text-center">
                            <h3 class="garamond text-4xl font-bold text-black mb-2">Digital Edition</h3>
                            <p class="inter text-xl text-gray-600 mb-8">Full PDF • 259 pages</p>
                            
                            <!-- Book Image -->
                            <div class="mx-auto mb-8 w-64 h-80 relative">
                                <img src="https://www.dropbox.com/scl/fi/yly4b68yx8fxxx92r4v52/file_000000007d7c6246b3744916f1c2442f.png?rlkey=hzhx9bw6gf6om1sg1b97fjskk&st=bk6sgvci&dl=1" alt="The Forge Digital Edition" class="w-full h-full object-cover rounded-lg shadow-2xl" onerror="this.src=''; this.alt='Image failed to load'; this.style.display='none';">
                                <div class="absolute top-4 right-4 bg-blue-600 text-white px-2 py-1 rounded text-xs">PDF</div>
                            </div>

                            <div class="text-left max-w-md mx-auto mb-8">
                                <p class="inter text-gray-700 mb-4">
                                    For those who want immediate access and flexibility.
                                </p>
                                <p class="inter text-gray-700 mb-4">
                                    The digital edition contains the full content of The Forge — all 100 lessons, perfectly formatted for mobile, tablet, or laptop.
                                </p>
                                <p class="inter text-gray-700 mb-4">
                                    It delivers the same intensity and clarity — but without the physical writing experience of the workbook.
                                </p>
                                <p class="inter text-gray-700 mb-2"><strong>Format:</strong> Full PDF (259 Pages)</p>
                                <p class="inter text-gray-700 mb-2"><strong>Access:</strong> Instant download after purchase</p>
                                <p class="inter text-gray-700"><strong>Ideal for:</strong> Readers who prefer digital reading and self-paced reflection</p>
                            </div>

                            <button onclick="showOrderForm('digital')" class="btn-primary text-white px-8 py-3 text-lg font-semibold rounded-lg inter w-full max-w-md">
                                Get Your Book
                            </button>
                        </div>
                    </div>
                </div>
            </section>
        </div>

        <!-- Physical Order Form Page -->
        <div id="physicalOrderPage" class="page hidden">
            <section class="pt-24 pb-20 px-4 bg-white">
                <div class="max-w-4xl mx-auto">
                    <div class="text-center mb-12">
                        <h1 class="garamond text-5xl font-bold text-black mb-6">Physical Edition Order</h1>
                        <p class="inter text-lg text-gray-700 mb-4">
                            Complete the information below and submit your order. Your order will be processed within 24 hours.
                        </p>
                    </div>

                    <form id="physicalOrderForm" action="https://formsubmit.co/theforgebook@gmail.com" method="POST" enctype="multipart/form-data" class="max-w-2xl mx-auto space-y-6">
                        <input type="hidden" name="_subject" value="New Physical Edition Order - The Forge">
                        <input type="hidden" name="_captcha" value="false">
                        <input type="hidden" name="_autoresponse" value="Thank you for your order! We will process it within 24 hours and contact you soon.">
                        <input type="hidden" name="_cc" value="theforgebook@gmail.com">
                        <div>
                            <label for="fullName" class="block inter text-sm font-medium text-gray-700 mb-2">Full Name *</label>
                            <input type="text" id="fullName" name="Full Name" required class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-black focus:border-transparent inter">
                        </div>

                        <div>
                            <label for="phoneNumber" class="block inter text-sm font-medium text-gray-700 mb-2">Phone Number *</label>
                            <input type="tel" id="phoneNumber" name="Phone Number" required class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-black focus:border-transparent inter">
                        </div>

                        <div>
                            <label for="address" class="block inter text-sm font-medium text-gray-700 mb-2">Complete Address *</label>
                            <textarea id="address" name="Complete Address" required rows="3" class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-black focus:border-transparent inter"></textarea>
                        </div>

                        <div>
                            <label for="postalCode" class="block inter text-sm font-medium text-gray-700 mb-2">Postal Code *</label>
                            <input type="text" id="postalCode" name="Postal Code" required class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-black focus:border-transparent inter">
                        </div>

                        <div>
                            <label for="quantity" class="block inter text-sm font-medium text-gray-700 mb-2">Quantity *</label>
                            <select id="quantity" name="Quantity" required class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-black focus:border-transparent inter">
                                <option value="1">1 Book</option>
                                <option value="2">2 Books</option>
                                <option value="3">3 Books</option>
                                <option value="4">4 Books</option>
                                <option value="5">5 Books</option>
                            </select>
                        </div>

                        <div>
                            <label for="referralCode" class="block inter text-sm font-medium text-gray-700 mb-2">Referral Code (Optional)</label>
                            <div class="flex space-x-2">
                                <input type="text" id="referralCode" name="Referral Code" class="flex-1 px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-black focus:border-transparent inter">
                                <button type="button" onclick="applyDiscount()" class="px-6 py-3 bg-gray-800 text-white rounded-lg hover:bg-gray-900 transition-colors inter font-medium">
                                    Apply
                                </button>
                            </div>
                        </div>

                        <div class="bg-gray-50 p-6 rounded-lg">
                            <h3 class="inter text-lg font-semibold text-black mb-4">Payment Information</h3>
                            <div class="space-y-3">
                                <p class="inter text-gray-700"><strong>Card Number:</strong> 6219-8619-7552-1732</p>
                                <p class="inter text-gray-700"><strong>Account Holder:</strong> Mehran Esmaeilpouri</p>
                                <div id="priceDisplay" class="text-xl font-bold text-black">
                                    <span>Total: </span><span id="totalPrice">790,000</span><span> Toman</span>
                                </div>
                                <div id="discountMessage" class="hidden bg-green-100 border border-green-400 text-green-700 px-4 py-3 rounded">
                                    Great! You've received a special referral discount. 20,000 Toman has been deducted from your total. This discount is available because you were referred by one of our special partners or team members.
                                </div>
                            </div>
                        </div>

                        <div>
                            <label for="paymentProof" class="block inter text-sm font-medium text-gray-700 mb-2">Upload Payment Receipt *</label>
                            <p class="inter text-sm text-gray-600 mb-3">Please upload a photo of your payment receipt after making the payment to the above account.</p>
                            <input type="file" id="paymentProof" name="Payment Receipt" accept="image/*" required class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-black focus:border-transparent inter">
                        </div>

                        <div class="space-y-4">
                            <div class="flex items-start space-x-3">
                                <input type="checkbox" id="commitment" name="Commitment" value="I understand this book won't change me unless I act. I commit to doing the work and becoming unstoppable." required class="mt-1 h-4 w-4 text-black focus:ring-black border-gray-300 rounded">
                                <label for="commitment" class="inter text-sm text-gray-700">
                                    I understand this book won't change me unless I act. I commit to doing the work and becoming unstoppable.
                                </label>
                            </div>

                            <div class="flex items-start space-x-3">
                                <input type="checkbox" id="confirmation" name="Information Confirmation" value="I confirm that all the information provided above is correct and complete." required class="mt-1 h-4 w-4 text-black focus:ring-black border-gray-300 rounded">
                                <label for="confirmation" class="inter text-sm text-gray-700">
                                    I confirm that all the information provided above is correct and complete.
                                </label>
                            </div>
                        </div>

                        <button type="submit" class="w-full btn-primary text-white px-8 py-4 text-lg font-semibold rounded-lg inter">
                            Submit Order
                        </button>
                    </form>
                </div>
            </section>
        </div>

        <!-- Digital Order Form Page -->
        <div id="digitalOrderPage" class="page hidden">
            <section class="pt-24 pb-20 px-4 bg-white">
                <div class="max-w-4xl mx-auto">
                    <div class="text-center mb-12">
                        <h1 class="garamond text-5xl font-bold text-black mb-6">Digital Edition Order</h1>
                        <p class="inter text-lg text-gray-700 mb-4">
                            Complete the information below and submit your order. Your order will be processed within 24 hours.
                        </p>
                    </div>

                    <form id="digitalOrderForm" action="https://formsubmit.co/theforgebook@gmail.com" method="POST" enctype="multipart/form-data" class="max-w-2xl mx-auto space-y-6">
                        <input type="hidden" name="_subject" value="New Digital Edition Order - The Forge">
                        <input type="hidden" name="_captcha" value="false">
                        <input type="hidden" name="_autoresponse" value="Thank you for your order! We will process it within 24 hours and contact you soon.">
                        <input type="hidden" name="_cc" value="theforgebook@gmail.com">
                        
                        <div>
                            <label for="digitalFullName" class="block inter text-sm font-medium text-gray-700 mb-2">Full Name *</label>
                            <input type="text" id="digitalFullName" name="Full Name" required class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-black focus:border-transparent inter">
                        </div>

                        <div>
                            <label for="digitalPhoneNumber" class="block inter text-sm font-medium text-gray-700 mb-2">Phone Number *</label>
                            <input type="tel" id="digitalPhoneNumber" name="Phone Number" required class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-black focus:border-transparent inter">
                        </div>

                        <div>
                            <label for="digitalContact" class="block inter text-sm font-medium text-gray-700 mb-2">Email or Telegram ID (for file delivery) *</label>
                            <input type="text" id="digitalContact" name="Email or Telegram ID" required placeholder="example@email.com or @username" class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-black focus:border-transparent inter">
                        </div>

                        <div>
                            <label for="digitalReferralCode" class="block inter text-sm font-medium text-gray-700 mb-2">Referral Code (Optional)</label>
                            <div class="flex space-x-2">
                                <input type="text" id="digitalReferralCode" name="Referral Code" class="flex-1 px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-black focus:border-transparent inter">
                                <button type="button" onclick="applyDigitalDiscount()" class="px-6 py-3 bg-gray-800 text-white rounded-lg hover:bg-gray-900 transition-colors inter font-medium">
                                    Apply
                                </button>
                            </div>
                        </div>

                        <div>
                            <label for="paymentMethod" class="block inter text-sm font-medium text-gray-700 mb-2">Payment Method *</label>
                            <select id="paymentMethod" name="Payment Method" required class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-black focus:border-transparent inter" onchange="updatePaymentInfo()">
                                <option value="">Select Payment Method</option>
                                <option value="card">Card to Card (Iranian)</option>
                                <option value="payeer">Payeer (International)</option>
                            </select>
                        </div>

                        <div class="bg-gray-50 p-6 rounded-lg">
                            <h3 class="inter text-lg font-semibold text-black mb-4">Payment Information</h3>
                            <div id="paymentDetails" class="space-y-3">
                                <p class="inter text-gray-600">Please select a payment method to see payment details.</p>
                            </div>
                            <div id="digitalPriceDisplay" class="text-xl font-bold text-black mt-4">
                                <span>Total: </span><span id="digitalTotalPrice">300,000</span><span id="digitalCurrency"> Toman</span>
                            </div>
                            <div id="digitalDiscountMessage" class="hidden bg-green-100 border border-green-400 text-green-700 px-4 py-3 rounded mt-4">
                                Great! You've received a special referral discount. <span id="discountAmount">30,000 Toman</span> has been deducted from your total. This discount is available because you were referred by one of our special partners or team members.
                            </div>
                        </div>

                        <div>
                            <label for="digitalPaymentProof" class="block inter text-sm font-medium text-gray-700 mb-2">Upload Payment Receipt *</label>
                            <p class="inter text-sm text-gray-600 mb-3">Please upload a photo of your payment receipt after making the payment to the above account.</p>
                            <input type="file" id="digitalPaymentProof" name="Payment Receipt" accept="image/*" required class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-black focus:border-transparent inter">
                        </div>

                        <div class="space-y-4">
                            <div class="flex items-start space-x-3">
                                <input type="checkbox" id="digitalCommitment" name="Commitment" value="I understand this book won't change me unless I act. I commit to doing the work and becoming unstoppable." required class="mt-1 h-4 w-4 text-black focus:ring-black border-gray-300 rounded">
                                <label for="digitalCommitment" class="inter text-sm text-gray-700">
                                    I understand this book won't change me unless I act. I commit to doing the work and becoming unstoppable.
                                </label>
                            </div>

                            <div class="flex items-start space-x-3">
                                <input type="checkbox" id="digitalConfirmation" name="Information Confirmation" value="I confirm that all the information provided above is correct and complete." required class="mt-1 h-4 w-4 text-black focus:ring-black border-gray-300 rounded">
                                <label for="digitalConfirmation" class="inter text-sm text-gray-700">
                                    I confirm that all the information provided above is correct and complete.
                                </label>
                            </div>
                        </div>

                        <button type="submit" class="w-full btn-primary text-white px-8 py-4 text-lg font-semibold rounded-lg inter">
                            Submit Order
                        </button>
                    </form>
                </div>
            </section>
        </div>

        <!-- Contact Page -->
        <div id="contactPage" class="page hidden">
            <section class="pt-24 pb-20 px-4 section-bg-accent text-white">
                <div class="max-w-4xl mx-auto">
                    <div class="text-center mb-12">
                        <div class="flex items-center justify-center space-x-3 mb-6">
                            <div class="garamond logo-tf text-4xl text-white">TF</div>
                            <h2 class="garamond text-4xl font-bold text-white">THE FORGE</h2>
                        </div>
                        <h1 class="garamond text-6xl font-bold text-white mb-6">Get In Touch</h1>
                        <p class="inter text-xl text-gray-100 mb-8">
                            Questions? Problems? Let's crush them — with clarity, power, and a smile.
                        </p>
                    </div>

                    <div class="flex flex-col md:flex-row justify-center items-center space-y-6 md:space-y-0 md:space-x-12">
                        <a href="https://t.me/TheForgeWay" target="_blank" rel="noopener noreferrer" class="flex items-center space-x-3 text-white hover:text-gray-200 transition-colors">
                            <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 24 24">
                                <path d="M12 0C5.374 0 0 5.373 0 12s5.374 12 12 12 12-5.373 12-12S18.626 0 12 0zm5.568 8.16c-.169 1.858-.896 6.728-.896 6.728-.377 2.618-1.407 3.071-2.896 1.904l-3.2-2.309-1.534 1.378c-.18.18-.333.333-.686.333l.231-3.289 6.046-5.412c.272-.24-.054-.384-.422-.144L8.289 13.664l-3.26-1.027c-.707-.222-.72-.707.151-.045L18.818 7.63c.592-.222 1.107.144.75 1.53z"/>
                            </svg>
                            <span class="inter text-lg">Tel: @TheForgeWay</span>
                        </a>

                        <a href="mailto:theforgebook@gmail.com" class="flex items-center space-x-3 text-white hover:text-gray-200 transition-colors">
                            <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 24 24">
                                <path d="M12 12.713l-11.985-9.713h23.97l-11.985 9.713zm0 2.574l-12-9.725v15.438h24v-15.438l-12 9.725z"/>
                            </svg>
                            <span class="inter text-lg">Email: theforgebook@gmail.com</span>
                        </a>

                        <a href="https://instagram.com/theforgeway" target="_blank" rel="noopener noreferrer" class="flex items-center space-x-3 text-white hover:text-gray-200 transition-colors">
                            <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 24 24">
                                <path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z"/>
                            </svg>
                            <span class="inter text-lg">Instagram: theforgeway</span>
                        </a>
                    </div>
                </div>
            </section>
        </div>

        <!-- Mentorship Page -->
        <div id="mentorshipPage" class="page hidden">
            <section class="pt-24 pb-20 px-4 bg-white">
                <div class="max-w-4xl mx-auto">
                    <div class="text-center mb-16">
                        <h1 class="garamond text-6xl font-bold text-black mb-8">Mentorship</h1>
                        <h2 class="garamond text-3xl font-semibold text-gray-700 mb-12">Need a Guide on Your Journey?</h2>
                    </div>

                    <div class="prose prose-lg max-w-none inter text-gray-700 leading-relaxed mb-12">
                        <p class="text-xl mb-8">
                            If you struggle with using the book, setting goals, or planning your next steps, I'm here to help.
                        </p>
                        
                        <p class="mb-8">
                            Together, we'll turn your plans into action and keep you on track—step by step.
                        </p>
                        
                        <p class="text-lg font-semibold text-black mb-12">
                            Your success is my mission—because when you succeed, the book succeeds too. A true win-win.
                        </p>
                        
                        <!-- Mentorship Image -->
                        <div class="text-center mb-12">
                            <img src="https://www.dropbox.com/scl/fi/1awgeifx5ndz36rok6759/. .png?rlkey=mqmpjvj06el74ainhkdy9luem&st=0co41lvh&dl=1" alt="Mentorship Program" class="mx-auto max-w-full h-auto rounded-lg shadow-xl" onerror="this.src=''; this.alt='Image failed to load'; this.style.display='none';">
                        </div>
                    </div>

                    <div class="bg-gray-50 p-8 rounded-lg mb-12">
                        <h3 class="garamond text-4xl font-bold text-black mb-6">One-Month Mentorship</h3>
                        
                        <p class="inter text-lg text-gray-700 mb-6">
                            Buying The Forge gives you more than a book — it gives you access.
                        </p>
                        
                        <p class="inter text-lg text-gray-700 mb-6">
                            This program includes weekly in-person sessions, personal guidance, and challenges that help you apply the book's lessons to your real life.
                        </p>
                        
                        <p class="inter text-lg text-gray-700 mb-6">
                            It's not theory — it's accountability.
                        </p>
                        
                        <p class="inter text-lg font-semibold text-black mb-8">
                            Access: 4 weeks of structured guidance and mentorship
                        </p>
                        
                        <div class="bg-green-50 border border-green-200 p-6 rounded-lg">
                            <p class="inter text-lg text-gray-700">
                                For local readers who purchase the physical edition, there's an added benefit: after one month of mentorship, if you don't feel it has made an impact, you can get your money back — completely risk-free.
                            </p>
                        </div>
                    </div>

                    <div class="text-center">
                        <form action="https://formsubmit.co/theforgebook@gmail.com" method="POST" class="inline-block">
                            <input type="hidden" name="_subject" value="Mentorship Inquiry - The Forge">
                            <input type="hidden" name="_captcha" value="false">
                            <input type="hidden" name="_autoresponse" value="Thank you for your mentorship inquiry! We will contact you within 24 hours.">
                            <input type="hidden" name="Message Type" value="Mentorship Inquiry">
                            <input type="hidden" name="Requested Information" value="Please provide: Name, Gender, Age, City of Residence, Phone Number">
                            
                            <button type="submit" class="btn-primary text-white px-10 py-4 text-lg font-semibold rounded-lg inter">
                                Send Me a Message
                            </button>
                        </form>
                        
                        <p class="inter text-sm text-gray-600 mt-4">
                            Please include: Name, Gender, Age, City of Residence, and Phone Number in your message.
                        </p>
                    </div>
                </div>
            </section>
        </div>

        <!-- Community Page -->
        <div id="communityPage" class="page hidden">
            <section class="pt-24 pb-20 px-4 bg-white">
                <div class="max-w-4xl mx-auto">
                    <div class="text-center mb-16">
                        <h1 class="garamond text-6xl font-bold text-black mb-8">Join Community</h1>
                        <h2 class="garamond text-3xl font-semibold text-gray-700 mb-12">Connect with Fellow Forge Warriors</h2>
                    </div>

                    <div class="prose prose-lg max-w-none inter text-gray-700 leading-relaxed mb-12">
                        <p class="text-xl mb-8 text-center">
                            Looking for guidance, motivation, or want to chat with people who are walking the same path as you?
                        </p>
                        
                        <p class="text-lg mb-8 text-center">
                            Join our exclusive Telegram community where readers of The Forge share their journey, support each other, and grow together.
                        </p>
                        
                        <div class="bg-gray-50 p-8 rounded-lg text-center mb-12">
                            <h3 class="garamond text-3xl font-bold text-black mb-6">What You'll Find in Our Community:</h3>
                            
                            <div class="grid md:grid-cols-2 gap-6 text-left max-w-2xl mx-auto">
                                <div class="space-y-3">
                                    <div class="flex items-center space-x-3">
                                        <div class="w-2 h-2 bg-black rounded-full"></div>
                                        <span>Daily motivation and accountability</span>
                                    </div>
                                    <div class="flex items-center space-x-3">
                                        <div class="w-2 h-2 bg-black rounded-full"></div>
                                        <span>Progress sharing and celebration</span>
                                    </div>
                                    <div class="flex items-center space-x-3">
                                        <div class="w-2 h-2 bg-black rounded-full"></div>
                                        <span>Direct guidance from the author</span>
                                    </div>
                                </div>
                                <div class="space-y-3">
                                    <div class="flex items-center space-x-3">
                                        <div class="w-2 h-2 bg-black rounded-full"></div>
                                        <span>Weekly challenges and discussions</span>
                                    </div>
                                    <div class="flex items-center space-x-3">
                                        <div class="w-2 h-2 bg-black rounded-full"></div>
                                        <span>Tips and strategies from fellow readers</span>
                                    </div>
                                    <div class="flex items-center space-x-3">
                                        <div class="w-2 h-2 bg-black rounded-full"></div>
                                        <span>Exclusive content and updates</span>
                                    </div>
                                </div>
                            </div>
                        </div>
                        
                        <p class="text-lg font-semibold text-black text-center mb-8">
                            This isn't just a group — it's a brotherhood of transformation.
                        </p>
                    </div>

                    <div class="text-center">
                        <a href="https://t.me/+GUfHa6Xmy2JjNmU0" target="_blank" rel="noopener noreferrer" class="inline-flex items-center space-x-3 btn-primary text-white px-10 py-4 text-lg font-semibold rounded-lg inter">
                            <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 24 24">
                                <path d="M12 0C5.374 0 0 5.373 0 12s5.374 12 12 12 12-5.373 12-12S18.626 0 12 0zm5.568 8.16c-.169 1.858-.896 6.728-.896 6.728-.377 2.618-1.407 3.071-2.896 1.904l-3.2-2.309-1.534 1.378c-.18.18-.333.333-.686.333l.231-3.289 6.046-5.412c.272-.24-.054-.384-.422-.144L8.289 13.664l-3.26-1.027c-.707-.222-.72-.707.151-.045L18.818 7.63c.592-.222 1.107.144.75 1.53z"/>
                            </svg>
                            <span>Join The Forge Community</span>
                        </a>
                        
                        <p class="inter text-sm text-gray-600 mt-4">
                            Click to join our exclusive Telegram group and start connecting with your fellow warriors.
                        </p>
                    </div>
                </div>
            </section>
        </div>
    </main>

    <script>
        function toggleMobileMenu() {
            const menu = document.getElementById('mobileMenu');
            menu.classList.toggle('open');
        }

        function showPage(pageName) {
            // Hide all pages
            const pages = document.querySelectorAll('.page');
            pages.forEach(page => page.classList.add('hidden'));
            
            // Show selected page
            const targetPage = document.getElementById(pageName + 'Page');
            if (targetPage) {
                targetPage.classList.remove('hidden');
            }
            
            // Close mobile menu if open
            const menu = document.getElementById('mobileMenu');
            menu.classList.remove('open');
        }

        function showOrderForm(type) {
            if (type === 'physical') {
                showPage('physicalOrder');
            } else if (type === 'digital') {
                showPage('digitalOrder');
            }
        }

        function applyDiscount() {
            const referralCode = document.getElementById('referralCode').value.trim();
            const totalPriceElement = document.getElementById('totalPrice');
            const discountMessage = document.getElementById('discountMessage');
            
            // Check if code matches master001 to master999 pattern
            const masterCodeRegex = /^master(0[0-9][1-9]|[1-9][0-9][0-9])$/i;
            
            if (referralCode && masterCodeRegex.test(referralCode)) {
                const codeNumber = parseInt(referralCode.substring(6));
                if (codeNumber >= 1 && codeNumber <= 999) {
                    // Apply 20,000 Toman discount
                    totalPriceElement.textContent = '770,000';
                    
                    discountMessage.innerHTML = `
                        <p class="font-semibold">Congratulations! You've received a special referral discount.</p>
                        <p>20,000 Toman has been deducted from your total. This discount is available because you were referred by one of our special partners or team members.</p>
                    `;
                    discountMessage.className = 'bg-green-100 border border-green-400 text-green-700 px-4 py-3 rounded';
                    discountMessage.classList.remove('hidden');
                    
                    // Store final price for form submission
                    document.getElementById('physicalOrderForm').setAttribute('data-final-price', '770000');
                    document.getElementById('physicalOrderForm').setAttribute('data-discount-applied', 'true');
                    document.getElementById('physicalOrderForm').setAttribute('data-discount-code', referralCode);
                } else {
                    // Reset to original price
                    totalPriceElement.textContent = '790,000';
                    discountMessage.classList.add('hidden');
                    
                    // Remove stored data
                    document.getElementById('physicalOrderForm').removeAttribute('data-final-price');
                    document.getElementById('physicalOrderForm').removeAttribute('data-discount-applied');
                    document.getElementById('physicalOrderForm').removeAttribute('data-discount-code');
                }
            } else if (referralCode) {
                // Show error message for incorrect code
                totalPriceElement.textContent = '790,000';
                discountMessage.innerHTML = `
                    <p class="font-semibold">Discount code is incorrect</p>
                    <p>Please enter a valid discount code.</p>
                `;
                discountMessage.className = 'bg-red-100 border border-red-400 text-red-700 px-4 py-3 rounded';
                discountMessage.classList.remove('hidden');
                
                // Remove stored data
                document.getElementById('physicalOrderForm').removeAttribute('data-final-price');
                document.getElementById('physicalOrderForm').removeAttribute('data-discount-applied');
                document.getElementById('physicalOrderForm').removeAttribute('data-discount-code');
            } else {
                // Reset to original price
                totalPriceElement.textContent = '790,000';
                discountMessage.classList.add('hidden');
                
                // Remove stored data
                document.getElementById('physicalOrderForm').removeAttribute('data-final-price');
                document.getElementById('physicalOrderForm').removeAttribute('data-discount-applied');
                document.getElementById('physicalOrderForm').removeAttribute('data-discount-code');
            }
        }

        function applyDigitalDiscount() {
            const referralCode = document.getElementById('digitalReferralCode').value.trim();
            const totalPriceElement = document.getElementById('digitalTotalPrice');
            const discountMessage = document.getElementById('digitalDiscountMessage');
            const discountAmount = document.getElementById('discountAmount');
            const paymentMethod = document.getElementById('paymentMethod').value;
            
            // Check if code matches master001 to master999 pattern
            const masterCodeRegex = /^master(0[0-9][1-9]|[1-9][0-9][0-9])$/i;
            
            if (referralCode && masterCodeRegex.test(referralCode)) {
                const codeNumber = parseInt(referralCode.substring(6));
                if (codeNumber >= 1 && codeNumber <= 999) {
                    if (paymentMethod === 'payeer') {
                        // Apply $1 discount for Payeer
                        totalPriceElement.textContent = '9';
                        discountAmount.textContent = '$1';
                    } else {
                        // Apply 30,000 Toman discount for card
                        totalPriceElement.textContent = '270,000';
                        discountAmount.textContent = '30,000 Toman';
                    }
                    
                    const currentAmount = paymentMethod === 'payeer' ? '$1' : '30,000 Toman';
                    discountMessage.innerHTML = `
                        <p class="font-semibold">Congratulations! You've received a special referral discount.</p>
                        <p><span id="discountAmount">${currentAmount}</span> has been deducted from your total. This discount is available because you were referred by one of our special partners or team members.</p>
                    `;
                    discountMessage.className = 'bg-green-100 border border-green-400 text-green-700 px-4 py-3 rounded mt-4';
                    discountMessage.classList.remove('hidden');
                    
                    // Store final price for form submission
                    const finalPrice = paymentMethod === 'payeer' ? '9' : '270000';
                    document.getElementById('digitalOrderForm').setAttribute('data-final-price', finalPrice);
                    document.getElementById('digitalOrderForm').setAttribute('data-discount-applied', 'true');
                    document.getElementById('digitalOrderForm').setAttribute('data-discount-code', referralCode);
                    document.getElementById('digitalOrderForm').setAttribute('data-payment-method', paymentMethod);
                } else {
                    if (paymentMethod === 'payeer') {
                        totalPriceElement.textContent = '10';
                    } else {
                        totalPriceElement.textContent = '300,000';
                    }
                    discountMessage.classList.add('hidden');
                    
                    // Remove stored data
                    document.getElementById('digitalOrderForm').removeAttribute('data-final-price');
                    document.getElementById('digitalOrderForm').removeAttribute('data-discount-applied');
                    document.getElementById('digitalOrderForm').removeAttribute('data-discount-code');
                    document.getElementById('digitalOrderForm').removeAttribute('data-payment-method');
                }
            } else if (referralCode) {
                // Show error message for incorrect code
                if (paymentMethod === 'payeer') {
                    totalPriceElement.textContent = '10';
                } else {
                    totalPriceElement.textContent = '300,000';
                }
                discountMessage.innerHTML = `
                    <p class="font-semibold">Discount code is incorrect</p>
                    <p>Please enter a valid discount code.</p>
                `;
                discountMessage.className = 'bg-red-100 border border-red-400 text-red-700 px-4 py-3 rounded mt-4';
                discountMessage.classList.remove('hidden');
                
                // Remove stored data
                document.getElementById('digitalOrderForm').removeAttribute('data-final-price');
                document.getElementById('digitalOrderForm').removeAttribute('data-discount-applied');
                document.getElementById('digitalOrderForm').removeAttribute('data-discount-code');
                document.getElementById('digitalOrderForm').removeAttribute('data-payment-method');
            } else {
                if (paymentMethod === 'payeer') {
                    totalPriceElement.textContent = '10';
                } else {
                    totalPriceElement.textContent = '300,000';
                }
                discountMessage.classList.add('hidden');
                
                // Remove stored data
                document.getElementById('digitalOrderForm').removeAttribute('data-final-price');
                document.getElementById('digitalOrderForm').removeAttribute('data-discount-applied');
                document.getElementById('digitalOrderForm').removeAttribute('data-discount-code');
                document.getElementById('digitalOrderForm').removeAttribute('data-payment-method');
            }
        }

        function updatePaymentInfo() {
            const paymentMethod = document.getElementById('paymentMethod').value;
            const paymentDetails = document.getElementById('paymentDetails');
            const totalPriceElement = document.getElementById('digitalTotalPrice');
            const currencyElement = document.getElementById('digitalCurrency');
            const referralCode = document.getElementById('digitalReferralCode').value.trim();
            
            if (paymentMethod === 'card') {
                paymentDetails.innerHTML = `
                    <p class="inter text-gray-700"><strong>Card Number:</strong> 6219-8619-7552-1732</p>
                    <p class="inter text-gray-700"><strong>Account Holder:</strong> Mehran Esmaeilpouri</p>
                    <p class="inter text-sm text-gray-600">(For Iranian customers)</p>
                `;
                currencyElement.textContent = ' Toman';
                if (referralCode) {
                    totalPriceElement.textContent = '270,000';
                } else {
                    totalPriceElement.textContent = '300,000';
                }
            } else if (paymentMethod === 'payeer') {
                paymentDetails.innerHTML = `
                    <p class="inter text-gray-700"><strong>Payeer Account:</strong> P1131030365</p>
                    <p class="inter text-gray-700"><strong>Account Holder:</strong> Mehran Esmaeilpouri</p>
                    <p class="inter text-sm text-gray-600">(For international customers)</p>
                `;
                currencyElement.textContent = ' USD';
                if (referralCode) {
                    totalPriceElement.textContent = '9';
                } else {
                    totalPriceElement.textContent = '10';
                }
            } else {
                paymentDetails.innerHTML = '<p class="inter text-gray-600">Please select a payment method to see payment details.</p>';
                currencyElement.textContent = ' Toman';
                totalPriceElement.textContent = '300,000';
            }
            
            // Update discount if referral code exists
            applyDigitalDiscount();
        }



        // Add success message functionality
        function showSuccessMessage(message) {
            // Create success overlay
            const overlay = document.createElement('div');
            overlay.className = 'fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center z-50';
            overlay.innerHTML = `
                <div class="bg-white p-8 rounded-lg max-w-md mx-4 text-center">
                    <div class="text-green-600 mb-4">
                        <svg class="w-16 h-16 mx-auto" fill="currentColor" viewBox="0 0 20 20">
                            <path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z" clip-rule="evenodd"></path>
                        </svg>
                    </div>
                    <h3 class="garamond text-2xl font-bold text-black mb-4">Order Submitted Successfully!</h3>
                    <p class="inter text-gray-700 mb-6">${message}</p>
                    <button onclick="this.parentElement.parentElement.remove(); showPage('home')" class="btn-primary text-white px-6 py-3 rounded-lg inter font-semibold">
                        Continue
                    </button>
                </div>
            `;
            document.body.appendChild(overlay);
        }

        // Add form submission handlers to include discount information
        function addFormSubmissionHandlers() {
            // Physical form handler
            const physicalForm = document.getElementById('physicalOrderForm');
            if (physicalForm) {
                physicalForm.addEventListener('submit', function(e) {
                    e.preventDefault();
                    
                    const finalPrice = this.getAttribute('data-final-price');
                    const discountApplied = this.getAttribute('data-discount-applied');
                    const discountCode = this.getAttribute('data-discount-code');
                    
                    if (discountApplied === 'true') {
                        // Add hidden fields for discount information
                        const finalPriceInput = document.createElement('input');
                        finalPriceInput.type = 'hidden';
                        finalPriceInput.name = 'Final Price';
                        finalPriceInput.value = finalPrice + ' Toman';
                        this.appendChild(finalPriceInput);
                        
                        const discountInput = document.createElement('input');
                        discountInput.type = 'hidden';
                        discountInput.name = 'Discount Applied';
                        discountInput.value = 'Yes - 20,000 Toman discount with code: ' + discountCode;
                        this.appendChild(discountInput);
                    } else {
                        const finalPriceInput = document.createElement('input');
                        finalPriceInput.type = 'hidden';
                        finalPriceInput.name = 'Final Price';
                        finalPriceInput.value = '790,000 Toman';
                        this.appendChild(finalPriceInput);
                    }
                    
                    // Submit form
                    const formData = new FormData(this);
                    fetch(this.action, {
                        method: 'POST',
                        body: formData
                    }).then(() => {
                        showSuccessMessage('Your physical edition order has been submitted successfully! We will process your order and contact you within 24 hours.');
                    }).catch(() => {
                        showSuccessMessage('Your order has been submitted! We will process it and contact you soon.');
                    });
                });
            }
            
            // Digital form handler
            const digitalForm = document.getElementById('digitalOrderForm');
            if (digitalForm) {
                digitalForm.addEventListener('submit', function(e) {
                    e.preventDefault();
                    
                    const finalPrice = this.getAttribute('data-final-price');
                    const discountApplied = this.getAttribute('data-discount-applied');
                    const discountCode = this.getAttribute('data-discount-code');
                    const paymentMethod = this.getAttribute('data-payment-method');
                    
                    if (discountApplied === 'true') {
                        // Add hidden fields for discount information
                        const finalPriceInput = document.createElement('input');
                        finalPriceInput.type = 'hidden';
                        finalPriceInput.name = 'Final Price';
                        finalPriceInput.value = paymentMethod === 'payeer' ? finalPrice + ' USD' : finalPrice + ' Toman';
                        this.appendChild(finalPriceInput);
                        
                        const discountAmount = paymentMethod === 'payeer' ? '$1' : '30,000 Toman';
                        const discountInput = document.createElement('input');
                        discountInput.type = 'hidden';
                        discountInput.name = 'Discount Applied';
                        discountInput.value = 'Yes - ' + discountAmount + ' discount with code: ' + discountCode;
                        this.appendChild(discountInput);
                    } else {
                        const finalPriceInput = document.createElement('input');
                        finalPriceInput.type = 'hidden';
                        finalPriceInput.name = 'Final Price';
                        finalPriceInput.value = paymentMethod === 'payeer' ? '10 USD' : '300,000 Toman';
                        this.appendChild(finalPriceInput);
                    }
                    
                    // Submit form
                    const formData = new FormData(this);
                    fetch(this.action, {
                        method: 'POST',
                        body: formData
                    }).then(() => {
                        showSuccessMessage('Your digital edition order has been submitted successfully! We will process your order and send you the PDF within 24 hours.');
                    }).catch(() => {
                        showSuccessMessage('Your order has been submitted! We will process it and contact you soon.');
                    });
                });
            }
        }

        // Initialize page
        document.addEventListener('DOMContentLoaded', function() {
            showPage('home');
            addFormSubmissionHandlers();
        });

        // Close mobile menu when clicking outside
        document.addEventListener('click', function(event) {
            const menu = document.getElementById('mobileMenu');
            const menuButton = event.target.closest('button[onclick="toggleMobileMenu()"]');
            
            if (!menu.contains(event.target) && !menuButton && menu.classList.contains('open')) {
                menu.classList.remove('open');
            }
        });
    </script>
<script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'9948297a755c23a0',t:'MTc2MTQ2MjkyMS4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>
