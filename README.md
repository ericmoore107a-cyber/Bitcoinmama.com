<!DOCTYPE html>
<html lang="en" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Securely buy, store, and manage Bitcoin. Trusted by over 500,000 users worldwide.">
    <title>BitForge • Secure Bitcoin Platform</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600&amp;family=Space+Grotesk:wght@500;600&amp;display=swap');
        
        :root {
            --gold: #f59e0b;
        }
        
        .tail-container {
            font-family: 'Inter', system_ui, sans-serif;
        }
        
        .heading-font {
            font-family: 'Space Grotesk', sans-serif;
        }

        .hero-bg {
            background: radial-gradient(at center bottom, #1e2937 0%, #0f172a 70%);
        }

        .nav-link {
            transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
        }
        
        .nav-link:hover {
            color: #f59e0b;
            transform: translateY(-2px);
        }

        .btc-price {
            animation: pricePulse 2s infinite;
        }

        @keyframes pricePulse {
            0%, 100% { opacity: 1; }
            50% { opacity: 0.85; }
        }

        .glass {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(12px);
        }

        .card-hover {
            transition: all 0.4s cubic-bezier(0.4, 0.0, 0.2, 1);
        }
        
        .card-hover:hover {
            transform: translateY(-8px);
            box-shadow: 0 25px 50px -12px rgb(245 158 11 / 0.15);
        }

        .glow-gold {
            box-shadow: 0 0 25px -5px rgb(245 158 11 / 0.5);
        }
    </style>
</head>
<body class="tail-container bg-zinc-950 text-zinc-200 overflow-x-hidden">
    <!-- NAVBAR -->
    <nav class="fixed top-0 left-0 right-0 z-50 border-b border-zinc-800 bg-zinc-950/80 backdrop-blur-lg">
        <div class="max-w-screen-2xl mx-auto px-6 py-5 flex items-center justify-between">
            <div class="flex items-center gap-x-3">
                <div class="w-9 h-9 bg-gradient-to-br from-amber-400 to-orange-500 rounded-2xl flex items-center justify-center text-xl font-bold">₿</div>
                <span class="heading-font text-3xl font-semibold tracking-tighter">BitForge</span>
            </div>
            
            <div class="hidden md:flex items-center gap-x-8 text-sm font-medium">
                <a href="#how" class="nav-link">How it works</a>
                <a href="#features" class="nav-link">Features</a>
                <a href="#security" class="nav-link">Security</a>
                <a href="#price" class="nav-link">Markets</a>
            </div>

            <div class="flex items-center gap-x-4">
                <button onclick="toggleLoginModal()" 
                        class="px-6 py-2.5 text-sm font-semibold hover:bg-white/10 rounded-2xl transition-colors">
                    Log in
                </button>
                <button onclick="showSignupModal()" 
                        class="px-6 py-2.5 bg-amber-500 hover:bg-amber-400 text-black font-semibold rounded-2xl transition-all active:scale-95">
                    Get Started
                </button>
            </div>
        </div>
    </nav>

    <!-- HERO -->
    <section class="hero-bg min-h-screen pt-24 flex items-center relative">
        <div class="absolute inset-0 bg-[radial-gradient(#27272a_1px,transparent_1px)] [background-size:40px_40px] opacity-30"></div>
        
        <div class="max-w-screen-2xl mx-auto px-6 grid md:grid-cols-2 gap-12 items-center">
            <div class="pt-12 md:pt-0">
                <div class="inline-flex items-center gap-x-2 bg-zinc-900 border border-amber-500/30 text-amber-400 text-sm px-4 py-2 rounded-3xl mb-6">
                    <div class="w-2 h-2 bg-emerald-400 rounded-full animate-pulse"></div>
                    Live on Bitcoin Mainnet
                </div>
                
                <h1 class="heading-font text-6xl md:text-7xl font-semibold tracking-tighter leading-none mb-6">
                    Own the future.<br>
                    <span class="bg-gradient-to-r from-amber-300 to-orange-400 bg-clip-text text-transparent">Secure it with Bitcoin.</span>
                </h1>
                
                <p class="text-xl text-zinc-400 max-w-lg mb-10">
                    The most trusted Bitcoin platform. Buy, sell, store, and send BTC with institutional-grade security.
                </p>
                
                <div class="flex flex-wrap gap-4">
                    <button onclick="showSignupModal()" 
                            class="px-8 py-5 bg-white text-black font-semibold text-lg rounded-3xl hover:bg-amber-300 transition-all active:scale-[0.97] flex items-center gap-x-3 group">
                        Start Buying Bitcoin
                        <i class="fa-solid fa-arrow-right group-active:translate-x-1 transition"></i>
                    </button>
                    
                    <button onclick="document.getElementById('price').scrollIntoView({ behavior: 'smooth' })" 
                            class="px-8 py-5 border border-zinc-700 hover:border-zinc-400 font-semibold text-lg rounded-3xl transition-all">
                        View Live Price
                    </button>
                </div>
                
                <!-- Trust badges -->
                <div class="flex items-center gap-x-8 mt-12 text-sm">
                    <div class="flex items-center gap-x-2">
                        <i class="fa-solid fa-shield-halved text-emerald-400"></i>
                        <span class="text-zinc-400">SOC 2 Certified</span>
                    </div>
                    <div class="flex items-center gap-x-2">
                        <i class="fa-solid fa-lock text-emerald-400"></i>
                        <span class="text-zinc-400">Bank-grade security</span>
                    </div>
                    <div class="flex items-center gap-x-2">
                        <span class="text-emerald-400 font-mono">99.99%</span>
                        <span class="text-zinc-400">Uptime</span>
                    </div>
                </div>
                
                <div class="mt-8 flex items-center gap-x-6 text-xs text-zinc-500">
                    <div class="flex -space-x-3">
                        <div class="w-6 h-6 bg-zinc-700 border-2 border-zinc-900 rounded-full"></div>
                        <div class="w-6 h-6 bg-amber-400 border-2 border-zinc-900 rounded-full"></div>
                    </div>
                    <p>Join <span class="font-semibold text-white">512,847</span> others securing their wealth</p>
                </div>
            </div>
            
            <!-- Hero visual -->
            <div class="relative hidden md:block">
                <div class="absolute -inset-10 bg-gradient-to-br from-amber-500/10 to-transparent rounded-[4rem] -rotate-6"></div>
                
                <div class="glass border border-white/10 rounded-3xl p-2 shadow-2xl relative">
                    <div class="bg-zinc-900 rounded-3xl p-8">
                        <!-- Mock wallet -->
                        <div class="flex justify-between items-start mb-8">
                            <div>
                                <div class="text-sm text-zinc-400">Your Balance</div>
                                <div id="hero-btc-balance" class="text-5xl font-mono font-semibold text-white">2.847 BTC</div>
                                <div id="hero-usd-balance" class="text-emerald-400 font-medium">$178,392.41</div>
                            </div>
                            <div class="text-right">
                                <div class="px-4 py-1 bg-emerald-500/10 text-emerald-400 text-xs rounded-2xl inline-flex items-center gap-x-1">
                                    <i class="fa-solid fa-arrow-trend-up"></i>
                                    <span>+4.82%</span>
                                </div>
                            </div>
                        </div>
                        
                        <!-- Price ticker in hero -->
                        <div class="bg-zinc-950 rounded-2xl p-5 mb-6">
                            <div class="flex items-center justify-between">
                                <div class="flex items-center gap-x-3">
                                    <div class="text-4xl">₿</div>
                                    <div>
                                        <div class="font-semibold">Bitcoin</div>
                                        <div id="hero-price" class="font-mono text-xl">62,847</div>
                                    </div>
                                </div>
                                <div id="hero-change" class="text-emerald-400 font-medium text-right">
                                    +1,284 (2.08%)
                                </div>
                            </div>
                        </div>
                        
                        <button onclick="showSignupModal()" 
                                class="w-full py-6 bg-gradient-to-r from-amber-400 to-orange-500 text-black font-semibold rounded-2xl text-lg hover:brightness-110 transition">
                            Buy Bitcoin Now
                        </button>
                    </div>
                </div>
                
                <!-- Floating badges -->
                <div class="absolute -top-6 -right-6 bg-zinc-900 border border-amber-400/30 text-amber-400 px-5 py-3 rounded-2xl text-sm flex items-center gap-x-2 shadow-xl">
                    <i class="fa-solid fa-circle-check"></i>
                    <span>Insured up to $250M</span>
                </div>
            </div>
        </div>
        
        <div class="absolute bottom-10 left-1/2 flex flex-col items-center">
            <div class="text-zinc-500 text-xs tracking-widest mb-2">SCROLL TO EXPLORE</div>
            <i class="fa-solid fa-chevron-down animate-bounce"></i>
        </div>
    </section>

    <!-- LIVE PRICE WIDGET -->
    <section id="price" class="py-8 border-b border-zinc-800 bg-black">
        <div class="max-w-screen-2xl mx-auto px-6">
            <div class="flex flex-col md:flex-row items-center justify-between gap-6 bg-zinc-900 rounded-3xl p-8">
                <div class="flex items-center gap-x-6">
                    <div class="flex items-center gap-x-4">
                        <span class="text-6xl">₿</span>
                        <div>
                            <div class="text-3xl font-semibold font-mono" id="live-price">62,847</div>
                            <div class="text-zinc-400">Bitcoin Price (USD)</div>
                        </div>
                    </div>
                    <div id="live-change" class="text-3xl font-medium text-emerald-400">+2.14%</div>
                </div>
                
                <div class="h-12 w-px bg-zinc-700 hidden md:block"></div>
                
                <div class="grid grid-cols-3 gap-x-12 text-sm">
                    <div>
                        <div class="text-zinc-400">Market Cap</div>
                        <div class="font-mono font-medium" id="market-cap">$1.24T</div>
                    </div>
                    <div>
                        <div class="text-zinc-400">24h Volume</div>
                        <div class="font-mono font-medium" id="volume">$38.2B</div>
                    </div>
                    <div>
                        <div class="text-zinc-400">All-time High</div>
                        <div class="font-mono font-medium">$73,837</div>
                    </div>
                </div>
                
                <button onclick="showSignupModal()" 
                        class="px-10 py-4 bg-amber-500 text-black font-semibold rounded-2xl hover:bg-amber-400 transition">
                    Buy BTC
                </button>
            </div>
        </div>
    </section>

    <!-- SOCIAL PROOF -->
    <section class="py-20 bg-zinc-950">
        <div class="max-w-screen-2xl mx-auto px-6">
            <div class="flex flex-wrap justify-center items-center gap-x-12 gap-y-8 opacity-75">
                <div class="text-2xl font-medium text-zinc-400">Forbes</div>
                <div class="text-2xl font-medium text-zinc-400">CoinDesk</div>
                <div class="text-2xl font-medium text-zinc-400">Bloomberg</div>
                <div class="text-2xl font-medium text-zinc-400">TechCrunch</div>
                <div class="text-2xl font-medium text-zinc-400">CNBC</div>
            </div>
            
            <div class="mt-20 grid md:grid-cols-3 gap-8">
                <!-- Testimonial 1 -->
                <div class="glass border border-white/5 p-8 rounded-3xl">
                    <div class="flex gap-x-1 text-amber-400 mb-6">
                        ★★★★☆
                    </div>
                    <p class="text-lg leading-relaxed">"Finally a Bitcoin platform I can trust. The security is unmatched and the interface is incredibly smooth."</p>
                    <div class="mt-8 flex items-center gap-x-3">
                        <div class="w-10 h-10 bg-zinc-700 rounded-2xl"></div>
                        <div>
                            <div class="font-semibold">Michael Chen</div>
                            <div class="text-sm text-zinc-400">Software Engineer • Singapore</div>
                        </div>
                    </div>
                </div>
                
                <!-- Testimonial 2 -->
                <div class="glass border border-white/5 p-8 rounded-3xl">
                    <div class="flex gap-x-1 text-amber-400 mb-6">
                        ★★★★★
                    </div>
                    <p class="text-lg leading-relaxed">"Moved my entire stack to BitForge after their cold storage demo. Best decision I've made in crypto."</p>
                    <div class="mt-8 flex items-center gap-x-3">
                        <div class="w-10 h-10 bg-orange-300 rounded-2xl"></div>
                        <div>
                            <div class="font-semibold">Aisha Okoro</div>
                            <div class="text-sm text-zinc-400">Entrepreneur • Lagos</div>
                        </div>
                    </div>
                </div>
                
                <!-- Testimonial 3 -->
                <div class="glass border border-white/5 p-8 rounded-3xl">
                    <div class="flex gap-x-1 text-amber-400 mb-6">
                        ★★★★★
                    </div>
                    <p class="text-lg leading-relaxed">"Instant withdrawals and zero drama. The team actually understands what Bitcoin users need."</p>
                    <div class="mt-8 flex items-center gap-x-3">
                        <div class="w-10 h-10 bg-sky-300 rounded-2xl"></div>
                        <div>
                            <div class="font-semibold">Carlos Rivera</div>
                            <div class="text-sm text-zinc-400">Investor • Mexico City</div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- HOW IT WORKS -->
    <section id="how" class="py-24 bg-black">
        <div class="max-w-screen-2xl mx-auto px-6">
            <div class="text-center mb-16">
                <span class="px-4 py-2 bg-zinc-900 rounded-3xl text-sm tracking-wider">3 STEPS</span>
                <h2 class="heading-font text-5xl font-semibold mt-4">Get started in minutes</h2>
            </div>
            
            <div class="grid md:grid-cols-3 gap-8">
                <div class="text-center card-hover bg-zinc-900 border border-zinc-800 rounded-3xl p-10">
                    <div class="w-20 h-20 mx-auto bg-gradient-to-br from-amber-400 to-orange-500 text-black rounded-3xl flex items-center justify-center text-4xl mb-8">1</div>
                    <h3 class="text-2xl font-semibold mb-3">Create Account</h3>
                    <p class="text-zinc-400">Sign up with email or Google. Verify in under 60 seconds.</p>
                </div>
                
                <div class="text-center card-hover bg-zinc-900 border border-zinc-800 rounded-3xl p-10">
                    <div class="w-20 h-20 mx-auto bg-gradient-to-br from-amber-400 to-orange-500 text-black rounded-3xl flex items-center justify-center text-4xl mb-8">2</div>
                    <h3 class="text-2xl font-semibold mb-3">Fund Your Wallet</h3>
                    <p class="text-zinc-400">Deposit via bank transfer, card, or crypto. Instant confirmation.</p>
                </div>
                
                <div class="text-center card-hover bg-zinc-900 border border-zinc-800 rounded-3xl p-10">
                    <div class="w-20 h-20 mx-auto bg-gradient-to-br from-amber-400 to-orange-500 text-black rounded-3xl flex items-center justify-center text-4xl mb-8">3</div>
                    <h3 class="text-2xl font-semibold mb-3">Buy &amp; Hold BTC</h3>
                    <p class="text-zinc-400">Purchase Bitcoin and secure it in your personal wallet.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- FEATURES -->
    <section id="features" class="py-24 bg-zinc-950">
        <div class="max-w-screen-2xl mx-auto px-6">
            <div class="grid md:grid-cols-12 gap-8">
                <div class="md:col-span-5">
                    <h2 class="heading-font text-5xl font-semibold leading-none">Built for serious Bitcoiners</h2>
                    <p class="mt-6 text-zinc-400 text-lg">Everything you need. Nothing you don't.</p>
                    
                    <div class="mt-12 space-y-6">
                        <div class="flex gap-x-6">
                            <i class="fa-solid fa-vault text-3xl text-amber-400 mt-1"></i>
                            <div>
                                <div class="font-semibold text-xl">Multi-Sig Cold Storage</div>
                                <div class="text-zinc-400">95% of funds stored offline in geographically distributed vaults.</div>
                            </div>
                        </div>
                        <div class="flex gap-x-6">
                            <i class="fa-solid fa-bolt text-3xl text-amber-400 mt-1"></i>
                            <div>
                                <div class="font-semibold text-xl">Lightning Network Ready</div>
                                <div class="text-zinc-400">Send and receive Bitcoin instantly with near-zero fees.</div>
                            </div>
                        </div>
                    </div>
                </div>
                
                <div class="md:col-span-7 grid grid-cols-1 sm:grid-cols-2 gap-6">
                    <div class="glass p-8 rounded-3xl card-hover border border-white/5">
                        <i class="fa-solid fa-shield-halved text-5xl text-emerald-400 mb-6"></i>
                        <div class="font-semibold text-2xl mb-2">Institutional Security</div>
                        <ul class="space-y-3 text-zinc-300">
                            <li class="flex items-center gap-x-2"><i class="fa-solid fa-check text-emerald-400"></i> 2FA + Biometrics</li>
                            <li class="flex items-center gap-x-2"><i class="fa-solid fa-check text-emerald-400"></i> Address whitelisting</li>
                            <li class="flex items-center gap-x-2"><i class="fa-solid fa-check text-emerald-400"></i> Insurance coverage</li>
                        </ul>
                    </div>
                    
                    <div class="glass p-8 rounded-3xl card-hover border border-white/5">
                        <i class="fa-solid fa-chart-line text-5xl text-sky-400 mb-6"></i>
                        <div class="font-semibold text-2xl mb-2">Advanced Tools</div>
                        <ul class="space-y-3 text-zinc-300">
                            <li class="flex items-center gap-x-2"><i class="fa-solid fa-check text-emerald-400"></i> DCA Automation</li>
                            <li class="flex items-center gap-x-2"><i class="fa-solid fa-check text-emerald-400"></i> Tax reports</li>
                            <li class="flex items-center gap-x-2"><i class="fa-solid fa-check text-emerald-400"></i> Portfolio analytics</li>
                        </ul>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- SECURITY -->
    <section id="security" class="py-24 bg-black">
        <div class="max-w-screen-2xl mx-auto px-6">
            <div class="grid md:grid-cols-2 gap-16 items-center">
                <div>
                    <span class="text-emerald-400 font-medium">YOUR ASSETS ARE PROTECTED</span>
                    <h2 class="heading-font text-5xl font-semibold mt-3 leading-tight">Security isn't a feature.<br>It's our foundation.</h2>
                    
                    <div class="mt-12 space-y-10">
                        <div class="flex gap-6">
                            <div class="shrink-0 w-12 h-12 bg-emerald-900/50 rounded-2xl flex items-center justify-center text-2xl">🔒</div>
                            <div>
                                <div class="font-semibold">Cold Storage</div>
                                <div class="text-zinc-400">Private keys never touch the internet. Audited quarterly.</div>
                            </div>
                        </div>
                        <div class="flex gap-6">
                            <div class="shrink-0 w-12 h-12 bg-emerald-900/50 rounded-2xl flex items-center justify-center text-2xl">🛡️</div>
                            <div>
                                <div class="font-semibold">End-to-End Encryption</div>
                                <div class="text-zinc-400">All data protected with AES-256 and zero-knowledge architecture.</div>
                            </div>
                        </div>
                        <div class="flex gap-6">
                            <div class="shrink-0 w-12 h-12 bg-emerald-900/50 rounded-2xl flex items-center justify-center text-2xl">📍</div>
                            <div>
                                <div class="font-semibold">Global Compliance</div>
                                <div class="text-zinc-400">KYC/AML compliant. Licensed in multiple jurisdictions.</div>
                            </div>
                        </div>
                    </div>
                </div>
                
                <div class="relative">
                    <div class="glass border-2 border-emerald-400/30 rounded-3xl p-12">
                        <div class="text-center">
                            <div class="mx-auto w-24 h-24 rounded-full border-8 border-emerald-400 flex items-center justify-center text-5xl mb-8">₿</div>
                            <div class="uppercase text-emerald-400 tracking-[3px] text-sm font-medium">Funds are SAFU</div>
                            <div class="text-4xl font-semibold mt-3">Protected by industry-leading infrastructure</div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- FINAL CTA -->
    <section class="py-28 bg-gradient-to-b from-transparent via-amber-500/5 to-transparent">
        <div class="max-w-2xl mx-auto text-center px-6">
            <h2 class="heading-font text-5xl font-bold">Ready to secure your financial freedom?</h2>
            <p class="mt-6 text-xl text-zinc-400">Join thousands of smart investors already holding Bitcoin on BitForge.</p>
            
            <button onclick="showSignupModal()" 
                    class="mt-10 px-12 py-7 text-2xl font-semibold bg-gradient-to-r from-amber-400 via-orange-400 to-amber-500 text-black rounded-3xl hover:scale-105 transition-transform">
                Create Free Account →
            </button>
            
            <p class="text-xs text-zinc-500 mt-8">No credit card required • Cancel anytime</p>
        </div>
    </section>

    <!-- FAQ -->
    <section class="py-24 bg-zinc-950">
        <div class="max-w-screen-2xl mx-auto px-6">
            <h2 class="text-center heading-font text-5xl font-semibold mb-16">Frequently Asked Questions</h2>
            
            <div class="max-w-3xl mx-auto space-y-4">
                <details class="group bg-zinc-900 rounded-3xl p-8">
                    <summary class="flex justify-between items-center cursor-pointer text-lg font-medium">
                        <span>Is my Bitcoin safe on BitForge?</span>
                        <i class="fa-solid fa-chevron-down group-open:rotate-180 transition"></i>
                    </summary>
                    <p class="mt-6 text-zinc-400">Yes. Over 95% of assets are held in offline cold storage. We also maintain full reserves and provide proof-of-reserves attestations.</p>
                </details>
                
                <details class="group bg-zinc-900 rounded-3xl p-8">
                    <summary class="flex justify-between items-center cursor-pointer text-lg font-medium">
                        <span>How quickly can I withdraw my funds?</span>
                        <i class="fa-solid fa-chevron-down group-open:rotate-180 transition"></i>
                    </summary>
                    <p class="mt-6 text-zinc-400">Bitcoin withdrawals are processed within 10-30 minutes during peak times. Fiat withdrawals usually arrive within 1 business day.</p>
                </details>
                
                <details class="group bg-zinc-900 rounded-3xl p-8">
                    <summary class="flex justify-between items-center cursor-pointer text-lg font-medium">
                        <span>What are the fees?</span>
                        <i class="fa-solid fa-chevron-down group-open:rotate-180 transition"></i>
                    </summary>
                    <p class="mt-6 text-zinc-400">Maker fees start at 0.10%. No hidden fees. Lightning Network transfers are often under $0.01.</p>
                </details>
            </div>
        </div>
    </section>

    <!-- FOOTER -->
    <footer class="bg-black pt-20 pb-12 border-t border-zinc-900">
        <div class="max-w-screen-2xl mx-auto px-6">
            <div class="grid md:grid-cols-5 gap-12">
                <div class="md:col-span-2">
                    <div class="flex items-center gap-x-3 mb-6">
                        <div class="w-9 h-9 bg-gradient-to-br from-amber-400 to-orange-500 rounded-2xl flex items-center justify-center text-3xl">₿</div>
                        <span class="heading-font text-4xl font-semibold tracking-tighter">BitForge</span>
                    </div>
                    <p class="text-zinc-400 max-w-xs">Bitcoin for the long term. Built with integrity.</p>
                    
                    <div class="mt-8 flex gap-x-5 text-2xl">
                        <i class="fa-brands fa-x-twitter cursor-pointer hover:text-amber-400 transition"></i>
                        <i class="fa-brands fa-telegram cursor-pointer hover:text-amber-400 transition"></i>
                    </div>
                </div>
                
                <div>
                    <div class="font-semibold mb-6">Product</div>
                    <div class="space-y-3 text-sm text-zinc-400">
                        <div>Buy Bitcoin</div>
                        <div>Wallet</div>
                        <div>Lightning</div>
                        <div>Learn</div>
                    </div>
                </div>
                
                <div>
                    <div class="font-semibold mb-6">Company</div>
                    <div class="space-y-3 text-sm text-zinc-400">
                        <div>About</div>
                        <div>Security</div>
                        <div>Careers</div>
                        <div>Blog</div>
                    </div>
                </div>
                
                <div>
                    <div class="font-semibold mb-6">Legal</div>
                    <div class="space-y-3 text-sm text-zinc-400">
                        <div>Privacy Policy</div>
                        <div>Terms of Service</div>
                        <div>Compliance</div>
                    </div>
                </div>
            </div>
            
            <div class="mt-20 pt-8 border-t border-zinc-800 text-xs text-zinc-500 flex flex-col md:flex-row justify-between items-center gap-4">
                <div>© 2026 BitForge Technologies. All rights reserved.</div>
                <div class="flex items-center gap-x-6">
                    <div class="flex items-center gap-x-1.5">
                        <div class="w-3 h-3 bg-emerald-400 rounded-full animate-pulse"></div>
                        <span>All systems operational</span>
                    </div>
                    <div>Lagos • Global</div>
                </div>
            </div>
        </div>
    </footer>

    <!-- SIGNUP MODAL -->
    <div id="signup-modal" class="hidden fixed inset-0 bg-black/80 backdrop-blur-xl z-[100] flex items-center justify-center">
        <div class="max-w-md w-full mx-4 bg-zinc-900 rounded-3xl p-10 relative">
            <button onclick="hideSignupModal()" class="absolute top-6 right-6 text-zinc-400 hover:text-white">✕</button>
            
            <div class="text-center mb-8">
                <div class="inline-flex items-center gap-x-2 text-amber-400 mb-4">
                    <span class="text-3xl">₿</span>
                    <span class="heading-font text-3xl font-bold">BitForge</span>
                </div>
                <h3 class="text-3xl font-semibold">Create your account</h3>
                <p class="text-zinc-400 mt-2">Start your Bitcoin journey today</p>
            </div>
            
            <div class="space-y-6">
                <div>
                    <label class="block text-sm mb-2 text-zinc-400">Email address</label>
                    <input id="email-input" type="email" 
                           class="w-full bg-zinc-800 border border-zinc-700 focus:border-amber-400 rounded-2xl px-6 py-5 outline-none transition" 
                           placeholder="you@email.com">
                </div>
                
                <button onclick="handleSignup()" 
                        class="w-full py-6 bg-gradient-to-r from-amber-400 to-orange-500 hover:brightness-110 text-black font-semibold rounded-2xl text-lg transition">
                    Continue with Email
                </button>
                
                <div class="relative text-center">
                    <div class="absolute inset-0 flex items-center">
                        <div class="w-full border-t border-zinc-700"></div>
                    </div>
                    <span class="relative bg-zinc-900 px-6 text-xs text-zinc-500">OR</span>
                </div>
                
                <button onclick="fakeGoogleSignup()" 
                        class="w-full py-6 border border-zinc-700 hover:bg-white/5 transition rounded-2xl flex items-center justify-center gap-x-3">
                    <i class="fa-brands fa-google"></i>
                    <span>Continue with Google</span>
                </button>
            </div>
            
            <p class="text-center text-xs text-zinc-500 mt-8">
                By signing up you agree to our <span class="underline">Terms</span>
            </p>
        </div>
    </div>

    <script>
        // Tailwind script already included via CDN
        
        function initTailwind() {
            // Already configured via script tag
        }
        
        // Live Bitcoin price simulation + real fetch
        async function fetchBitcoinPrice() {
            try {
                const res = await fetch('https://api.coingecko.com/api/v3/simple/price?ids=bitcoin&vs_currencies=usd&include_24hr_change=true');
                const data = await res.json();
                
                const price = Math.round(data.bitcoin.usd);
                const change = data.bitcoin.usd_24h_change.toFixed(2);
                
                document.getElementById('live-price').textContent = price.toLocaleString();
                document.getElementById('hero-price').textContent = price.toLocaleString();
                
                const changeEl = document.getElementById('live-change');
                changeEl.textContent = change > 0 ? `+${change}%` : `${change}%`;
                changeEl.className = change > 0 ? "text-3xl font-medium text-emerald-400" : "text-3xl font-medium text-red-400";
                
            } catch(e) {
                // Fallback values
                document.getElementById('live-price').textContent = "62847";
            }
        }
        
        // Fake balance animation
        function animateBalance() {
            let btc = 2.847;
            const interval = setInterval(() => {
                btc += 0.0003;
                document.getElementById('hero-btc-balance').textContent = btc.toFixed(3) + " BTC";
            }, 1800);
        }
        
        // Modal controls
        function showSignupModal() {
            document.getElementById('signup-modal').classList.remove('hidden');
            document.getElementById('signup-modal').classList.add('flex');
        }
        
        function hideSignupModal() {
            const modal = document.getElementById('signup-modal');
            modal.classList.add('hidden');
            modal.classList.remove('flex');
        }
        
        function toggleLoginModal() {
            alert("Login flow would open here in a real app. (Demo)");
        }
        
        function handleSignup() {
            const email = document.getElementById('email-input').value;
            if (email) {
                hideSignupModal();
                setTimeout(() => {
                    alert(`🎉 Welcome to BitForge! We've sent a confirmation link to ${email}`);
                }, 600);
            } else {
                alert("Please enter your email address");
            }
        }
        
        function fakeGoogleSignup() {
            hideSignupModal();
            setTimeout(() => {
                alert("✅ Connected via Google. Redirecting to your dashboard...");
            }, 400);
        }
        
        // Keyboard escape support
        document.addEventListener('keydown', function(e) {
            if (e.key === "Escape") {
                hideSignupModal();
            }
        });
        
        // Initialize everything
        window.onload = function() {
            fetchBitcoinPrice();
            animateBalance();
            
            // Refresh price every 30 seconds
            setInterval(fetchBitcoinPrice, 30000);
            
            // Demo: random small price fluctuation
            setInterval(() => {
                const priceEl = document.getElementById('live-price');
                let price = parseInt(priceEl.textContent.replace(',', ''));
                price += Math.floor(Math.random() * 17) - 8;
                priceEl.textContent = price.toLocaleString();
            }, 7000);
            
            console.log('%cBitForge demo loaded successfully. Ready for production.', 'color:#f59e0b; font-family:monospace');
        };
    </script>
</body>
</html>
