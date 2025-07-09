<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>TurboIG | Professional Social Hub</title>
    <script src="https://kit.fontawesome.com/a076d05399.js" crossorigin="anonymous"></script>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        :root {
            --primary: #6d28d9;
            --secondary: #8b5cf6;
            --dark: #1e1b4b;
            --light: #f5f3ff;
        }
        
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: var(--light);
            color: var(--dark);
        }
        
        .gradient-bg {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
        }
        
        .social-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.1);
        }
        
        .update-card {
            transition: all 0.3s ease;
            border-left: 4px solid var(--primary);
        }
        
        .update-card:hover {
            background-color: white;
            box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1);
        }
        
        .floating-btn {
            animation: float 3s ease-in-out infinite;
        }
        
        @keyframes float {
            0% { transform: translateY(0px); }
            50% { transform: translateY(-10px); }
            100% { transform: translateY(0px); }
        }
    </style>
</head>
<body class="min-h-screen">
    <!-- Luxury Navbar -->
    <nav class="gradient-bg text-white shadow-lg">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex items-center justify-between h-16">
                <div class="flex items-center">
                    <div class="flex-shrink-0">
                        <img src="https://storage.googleapis.com/workspace-0f70711f-8b4e-4d94-86f1-2a93ccde5887/image/3212db49-eda9-43d7-a14d-3bc1a1d32587.png" alt="TurboIG Logo in purple gradient with modern typography" class="h-8 w-8 rounded-full">
                    </div>
                    <div class="hidden md:block">
                        <div class="ml-10 flex items-baseline space-x-4">
                            <a href="#" class="px-3 py-2 rounded-md text-sm font-medium bg-black bg-opacity-25">Home</a>
                            <a href="#" class="px-3 py-2 rounded-md text-sm font-medium hover:bg-black hover:bg-opacity-25">Updates</a>
                            <a href="#" class="px-3 py-2 rounded-md text-sm font-medium hover:bg-black hover:bg-opacity-25">Features</a>
                            <a href="#" class="px-3 py-2 rounded-md text-sm font-medium hover:bg-black hover:bg-opacity-25">Contact</a>
                        </div>
                    </div>
                </div>
                <div class="hidden md:block">
                    <div class="ml-4 flex items-center md:ml-6">
                        <button class="p-1 rounded-full text-white hover:text-gray-300 focus:outline-none">
                            <span class="sr-only">View notifications</span>
                            <i class="fas fa-bell"></i>
                        </button>
                    </div>
                </div>
            </div>
        </div>
    </nav>

    <!-- Hero Section -->
    <div class="gradient-bg text-white py-20">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center">
                <h1 class="text-4xl md:text-6xl font-extrabold mb-6">Welcome to <span class="text-yellow-300">TurboIG</span></h1>
                <p class="text-xl md:text-2xl mb-8 max-w-3xl mx-auto">Your ultimate social media hub for exclusive updates and premium content</p>
                <div class="flex justify-center space-x-4">
                    <a href="#updates" class="px-8 py-3 bg-white text-purple-800 font-bold rounded-full hover:bg-gray-100">Explore Updates</a>
                    <a href="#social" class="px-8 py-3 border-2 border-white text-white font-bold rounded-full hover:bg-white hover:text-purple-800">Connect With Us</a>
                </div>
            </div>
        </div>
    </div>

    <!-- Social Links Section -->
    <div id="social" class="py-16 bg-white">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <h2 class="text-3xl font-extrabold text-center mb-12 text-gray-900">Connect With Us</h2>
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
                <!-- YouTube Card -->
                <div class="social-card bg-white rounded-xl shadow-md overflow-hidden transition duration-300">
                    <div class="p-6 text-center">
                        <div class="mx-auto h-16 w-16 rounded-full bg-red-100 flex items-center justify-center mb-4">
                            <i class="fab fa-youtube text-red-600 text-2xl"></i>
                        </div>
                        <h3 class="text-xl font-bold text-gray-900 mb-2">YouTube</h3>
                        <p class="text-gray-600 mb-4">Subscribe for premium content</p>
                        <a href="https://www.youtube.com/@Turboig" target="_blank" class="inline-block px-4 py-2 bg-red-600 text-white rounded-lg hover:bg-red-700">Visit Channel</a>
                    </div>
                </div>
                
                <!-- Telegram Card -->
                <div class="social-card bg-white rounded-xl shadow-md overflow-hidden transition duration-300">
                    <div class="p-6 text-center">
                        <div class="mx-auto h-16 w-16 rounded-full bg-blue-100 flex items-center justify-center mb-4">
                            <i class="fab fa-telegram text-blue-500 text-2xl"></i>
                        </div>
                        <h3 class="text-xl font-bold text-gray-900 mb-2">Telegram</h3>
                        <p class="text-gray-600 mb-4">Join our exclusive community</p>
                        <a href="https://t.me/turboig" target="_blank" class="inline-block px-4 py-2 bg-blue-500 text-white rounded-lg hover:bg-blue-600">Join Channel</a>
<
                    </div>
                </div>
                
                <!-- Discord Card -->
                <div class="social-card bg-white rounded-xl shadow-md overflow-hidden transition duration-300">
                    <div class="p-6 text-center">
                        <div class="mx-auto h-16 w-16 rounded-full bg-indigo-100 flex items-center justify-center mb-4">
                            <i class="fab fa-discord text-indigo-600 text-2xl"></i>
                        </div>
                        <h3 class="text-xl font-bold text-gray-900 mb-2">Discord</h3>
                        <p class="text-gray-600 mb-4">Connect with our community</p>
                        <a href="https://discord.gg/Gg5gcAJXT6" target="_blank" class="inline-block px-4 py-2 bg-indigo-600 text-white rounded-lg hover:bg-indigo-700">Join Server</a>
                    </div>
                </div>
                
                <!-- Instagram Card -->
                <div class="social-card bg-white rounded-xl shadow-md overflow-hidden transition duration-300">
                    <div class="p-6 text-center">
                        <div class="mx-auto h-16 w-16 rounded-full bg-pink-100 flex items-center justify-center mb-4">
                            <i class="fab fa-instagram text-pink-500 text-2xl"></i>
                        </div>
                        <h3 class="text-xl font-bold text-gray-900 mb-2">Instagram</h3>
                        <p class="text-gray-600 mb-4">Follow for latest updates</p>
                        <a href="https://instagram.com/yourprofile" target="_blank" class="inline-block px-4 py-2 bg-gradient-to-r from-purple-500 to-pink-500 text-white rounded-lg hover:opacity-90">Follow Us</a>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- Updates Section -->
    <div id="updates" class="py-16 bg-gray-50">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <h2 class="text-3xl font-extrabold text-center mb-12 text-gray-900">Latest Updates</h2>
            <div class="space-y-6">
                <!-- Update 1 -->
                <div class="update-card bg-white p-6 rounded-lg shadow-sm">
                    <div class="flex items-start">
                        <div class="flex-shrink-0 h-10 w-10 rounded-full bg-purple-100 flex items-center justify-center mr-4">
                            <i class="fas fa-rocket text-purple-600"></i>
                        </div>
                        <div class="flex-1">
                            <div class="flex items-center justify-between">
                                <h3 class="text-lg font-bold text-gray-900">New Content Series Launch</h3>
                                <span class="text-xs text-purple-600 bg-purple-50 px-2 py-1 rounded-full">New</span>
                            </div>
                            <p class="mt-1 text-gray-600">We're excited to announce our premium content series starting next week with exclusive insights.</p>
                            <div class="mt-3 flex items-center text-sm text-gray-500">
                                <i class="far fa-calendar-alt mr-1"></i>
                                <span>Posted 2 days ago</span>
                            </div>
                        </div>
                    </div>
                </div>
                
                <!-- Update 2 -->
                <div class="update-card bg-white p-6 rounded-lg shadow-sm">
                    <div class="flex items-start">
                        <div class="flex-shrink-0 h-10 w-10 rounded-full bg-blue-100 flex items-center justify-center mr-4">
                            <i class="fas fa-users text-blue-500"></i>
                        </div>
                        <div class="flex-1">
                            <div class="flex items-center justify-between">
                                <h3 class="text-lg font-bold text-gray-900">Community Milestone</h3>
                                <span class="text-xs text-blue-500 bg-blue-50 px-2 py-1 rounded-full">Achievement</span>
                            </div>
                            <p class="mt-1 text-gray-600">Our TurboIG Telegram community with exclusive content!</p>
                            <div class="mt-3 flex items-center text-sm text-gray-500">
                                <i class="far fa-calendar-alt mr-1"></i>
                                <span>Posted 1 week ago</span>
                            </div>
                        </div>
                    </div>
                </div>
                
                <!-- Update 3 -->
                <div class="update-card bg-white p-6 rounded-lg shadow-sm">
                    <div class="flex items-start">
                        <div class="flex-shrink-0 h-10 w-10 rounded-full bg-green-100 flex items-center justify-center mr-4">
                            <i class="fas fa-video text-green-500"></i>
                        </div>
                        <div class="flex-1">
                            <div class="flex items-center justify-between">
                                <h3 class="text-lg font-bold text-gray-900">Live Q&A Session</h3>
                                <span class="text-xs text-green-500 bg-green-50 px-2 py-1 rounded-full">Event</span>
                            </div>
                            <p class="mt-1 text-gray-600">Join us this Friday for a special live Q&A session on our YouTube channel.</p>
                            <div class="mt-3 flex items-center text-sm text-gray-500">
                                <i class="far fa-calendar-alt mr-1"></i>
                                <span>Posted 2 weeks ago</span>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            
            <div class="mt-10 text-center">
                <a href="#" class="inline-flex items-center px-4 py-2 border border-transparent text-sm font-medium rounded-md shadow-sm text-white gradient-bg hover:opacity-90">
                    View All Updates
                    <i class="fas fa-chevron-right ml-2"></i>
                </a>
            </div>
        </div>
    </div>

    <!-- Featured Section -->
    <div class="py-16 gradient-bg text-white">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="lg:grid lg:grid-cols-2 lg:gap-8 items-center">
                <div class="mb-10 lg:mb-0">
                    <h2 class="text-3xl font-extrabold mb-6">Why Join <span class="text-yellow-300">TurboIG</span>?</h2>
                    <p class="text-lg mb-6">Get access to premium content before anyone else. Our community gets exclusive insights, early releases, and special perks.</p>
                    <ul class="space-y-3">
                        <li class="flex items-start">
                            <div class="flex-shrink-0">
                                <i class="fas fa-check-circle text-yellow-300"></i>
                            </div>
                            <p class="ml-2 text-white">Exclusive content drops</p>
                        </li>
                        <li class="flex items-start">
                            <div class="flex-shrink-0">
                                <i class="fas fa-check-circle text-yellow-300"></i>
                            </div>
                            <p class="ml-2 text-white">24/7 community support</p>
                        </li>
                        <li class="flex items-start">
                            <div class="flex-shrink-0">
                                <i class="fas fa-check-circle text-yellow-300"></i>
                            </div>
                            <p class="ml-2 text-white">Special giveaways</p>
                        </li>
                        <li class="flex items-start">
                            <div class="flex-shrink-0">
                                <i class="fas fa-check-circle text-yellow-300"></i>
                            </div>
                            <p class="ml-2 text-white">Direct Q&A with creators</p>
                        </li>
                    </ul>
                </div>
                <div class="relative floating-btn">
                    <img src="https://storage.googleapis.com/workspace-0f70711f-8b4e-4d94-86f1-2a93ccde5887/image/c11997e7-91fd-4a71-8d9a-86e0e55a5e12.png" alt="Digital creator workspace showing multiple screens with social media analytics and content creation tools" class="rounded-xl shadow-2xl">
                    <div class="absolute -bottom-5 -left-5 bg-white rounded-lg p-3 shadow-lg">
                        <div class="flex items-center">
                            <div class="mr-3">
                                <i class="fas fa-play-circle text-purple-600 text-3xl"></i>
                            </div>
                            <div>
                                <p class="text-xs text-gray-500">Latest Video</p>
                                <p class="text-sm font-semibold text-gray-900">How to Grow Your Brand</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- Footer -->
    <footer class="bg-gray-900 text-white pt-16 pb-8">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="grid grid-cols-1 md:grid-cols-4 gap-8">
                <div>
                    <h3 class="text-lg font-semibold mb-4">TurboIG</h3>
                    <p class="text-gray-400">Your premium content hub for social media success and digital growth.</p>
                    <div class="flex space-x-4 mt-4">
                        <a href="#" class="text-gray-400 hover:text-white">
                            <i class="fab fa-facebook-f"></i>
                        </a>
                        <a href="#" class="text-gray-400 hover:text-white">
                            <i class="fab fa-twitter"></i>
                        </a>
                        <a href="#" class="text-gray-400 hover:text-white">
                            <i class="fab fa-instagram"></i>
                        </a>
                        <a href="#" class="text-gray-400 hover:text-white">
                            <i class="fab fa-linkedin-in"></i>
                        </a>
                    </div>
                </div>
                <div>
                    <h3 class="text-lg font-semibold mb-4">Quick Links</h3>
                    <ul class="space-y-2">
                        <li><a href="#" class="text-gray-400 hover:text-white">Home</a></li>
                        <li><a href="#" class="text-gray-400 hover:text-white">About</a></li>
                        <li><a href="#" class="text-gray-400 hover:text-white">Updates</a></li>
                        <li><a href="#" class="text-gray-400 hover:text-white">Contact</a></li>
                    </ul>
                </div>
                <div>
                    <h3 class="text-lg font-semibold mb-4">Support</h3>
                    <ul class="space-y-2">
                        <li><a href="#" class="text-gray-400 hover:text-white">FAQ</a></li>
                        <li><a href="#" class="text-gray-400 hover:text-white">Help Center</a></li>
                        <li><a href="#" class="text-gray-400 hover:text-white">Community</a></li>
                    </ul>
                </div>
                <div>
                    <h3 class="text-lg font-semibold mb-4">Newsletter</h3>
                    <p class="text-gray-400 mb-2">Subscribe to get exclusive updates</p>
                    <form class="flex">
                        <input type="email" placeholder="Your email" class="px-4 py-2 rounded-l-lg focus:outline-none text-gray-900 w-full">
                        <button type="submit" class="bg-purple-600 hover:bg-purple-700 px-4 py-2 rounded-r-lg">
                            <i class="fas fa-paper-plane"></i>
                        </button>
                    </form>
                </div>
            </div>
            <div class="border-t border-gray-800 mt-12 pt-8 flex flex-col md:flex-row justify-between items-center">
                <p class="text-gray-400 text-sm">© 2023 TurboIG. All rights reserved.</p>
                <div class="flex space-x-6 mt-4 md:mt-0">
                    <a href="#" class="text-gray-400 hover:text-white text-sm">Privacy Policy</a>
                    <a href="#" class="text-gray-400 hover:text-white text-sm">Terms of Service</a>
                </div>
            </div>
        </div>
    </footer>

    <!-- Floating Action Button -->
    <div class="fixed bottom-6 right-6">
        <a href="#" class="floating-btn h-14 w-14 gradient-bg rounded-full shadow-lg flex items-center justify-center text-white text-2xl hover:text-yellow-300">
            <i class="fas fa-paper-plane"></i>
        </a>
    </div>

    <script>
        // Simple animations
        document.addEventListener('DOMContentLoaded', function() {
            // Animate elements when they come into view
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.classList.add('animate_animated', 'animate_fadeInUp');
                        observer.unobserve(entry.target);
                    }
                });
            }, { threshold: 0.1 });
            
            document.querySelectorAll('.social-card, .update-card').forEach(card => {
                observer.observe(card);
            });
            
            // Smooth scrolling for anchor links
            document.querySelectorAll('a[href^="#"]').forEach(anchor => {
                anchor.addEventListener('click', function(e) {
                    e.preventDefault();
                    
                    document.querySelector(this.getAttribute('href')).scrollIntoView({
                        behavior: 'smooth'
                    });
                });
            });
        });
    </script>
</body>
</html>
