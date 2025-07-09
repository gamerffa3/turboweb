[<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Planet Vibe Server Dashboard</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap');
    
    body {
      font-family: 'Poppins', sans-serif;
      transition: all 0.3s ease;
      background-color: #f8fafc;
    }
    
    .dark {
      background-color: #1a1a1a;
      color: #f8fafc;
    }
    
    .card {
      transition: transform 0.3s ease, box-shadow 0.3s ease;
    }
    
    .card:hover {
      transform: translateY(-5px);
      box-shadow: 0 10px 20px rgba(0,0,0,0.1);
    }
    
    .dark .card:hover {
      box-shadow: 0 10px 20px rgba(255,255,255,0.1);
    }
    
    .pulse {
      animation: pulse 2s infinite;
    }
    
    @keyframes pulse {
      0% {
        opacity: 1;
      }
      50% {
        opacity: 0.7;
      }
      100% {
        opacity: 1;
      }
    }
    
    .server-status {
      height: 10px;
      width: 10px;
      border-radius: 50%;
      display: inline-block;
      margin-right: 5px;
    }
    
    .online {
      background-color: #10b981;
      box-shadow: 0 0 10px #10b981;
    }
    
    .offline {
      background-color: #ef4444;
    }
    
    .slide-in {
      animation: slideIn 1s forwards;
    }
    
    @keyframes slideIn {
      from {
        transform: translateX(-100%);
        opacity: 0;
      }
      to {
        transform: translateX(0);
        opacity: 1;
      }
    }
    
    .social-icon {
      transition: all 0.3s ease;
    }
    
    .social-icon:hover {
      transform: scale(1.2);
    }
    
    .floating {
      animation: floating 3s ease-in-out infinite;
    }
    
    @keyframes floating {
      0% { transform: translateY(0px); }
      50% { transform: translateY(-10px); }
      100% { transform: translateY(0px); }
    }
    
    .progress-bar {
      animation: progress 3s ease-in-out forwards;
    }
    
    @keyframes progress {
      from { width: 0; }
    }
  </style>
</head>
<body class="min-h-screen">
  <div class="container mx-auto px-4 py-8">
    <!-- Header -->
    <header class="flex justify-between items-center mb-8 slide-in">
      <h1 class="text-3xl font-bold bg-gradient-to-r from-blue-500 to-purple-600 bg-clip-text text-transparent"><span class="floating">🌍</span> Planet Vibe Dashboard</h1>
      <button id="themeToggle" class="p-2 rounded-full bg-gray-200 dark:bg-gray-700">
        <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-gray-800 dark:text-yellow-400" fill="none" viewBox="0 0 24 24" stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 3v1m0 16v1m9-9h-1M4 12H3m15.364 6.364l-.707-.707M6.343 6.343l-.707-.707m12.728 0l-.707.707M6.343 17.657l-.707.707M16 12a4 4 0 11-8 0 4 4 0 018 0z" />
        </svg>
      </button>
    </header>
    
    <!-- Server Info Card -->
    <div class="grid grid-cols-1 md:grid-cols-3 gap-6 mb-8">
      <div class="card bg-white dark:bg-gray-800 rounded-xl p-6 shadow-lg col-span-2">
        <div class="planet-vibe-status-plugin">
          <h2 class="text-xl font-semibold mb-4 flex items-center">
            <span class="server-status online pulse"></span>
            Planet Vibe Status
            <span id="refreshBtn" class="ml-2 cursor-pointer hover:text-blue-500">
              <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 4v5h.582m15.356 2A8.001 8.001 0 004.582 9m0 0H9m11 11v-5h-.581m0 0a8.003 8.003 0 01-15.357-2m15.357 2H15" />
              </svg>
            </span>
          </h2>
          
          <div class="space-y-4">
            <div class="server-stat">
              <div class="flex justify-between items-center">
                <span class="text-gray-600 dark:text-gray-300">Server IP:</span>
                <span id="serverIp" class="font-mono bg-gray-100 dark:bg-gray-700 px-3 py-1 rounded">Loading...</span>
              </div>
            </div>
            
            <div class="server-stat">
              <div class="flex justify-between items-center">
                <span class="text-gray-600 dark:text-gray-300">Status:</span>
                <span id="serverStatus" class="status-badge online">Online</span>
              </div>
            </div>
            
            <div class="server-stat">
              <div class="flex justify-between items-center">
                <span class="text-gray-600 dark:text-gray-300">Players:</span>
                <span id="playerCount" class="font-mono">0/100</span>
              </div>
              <div id="playerBar" class="mt-1 w-full bg-gray-200 rounded-full h-1.5 dark:bg-gray-700">
                <div class="bg-blue-600 h-1.5 rounded-full" style="width: 0%"></div>
              </div>
            </div>
            
            <div class="server-stat">
              <div class="flex justify-between items-center">
                <span class="text-gray-600 dark:text-gray-300">Last Ping:</span>
                <span id="lastPing" class="font-mono">0ms</span>
              </div>
            </div>
          </div>
        </div>
        
        <!-- Server Resources Graph -->
        <div class="mt-6">
          <h3 class="text-lg font-medium mb-2">Server Resources</h3>
          <div class="space-y-4">
            <div>
              <div class="flex justify-between mb-1">
                <span>CPU Usage</span>
                <span>65%</span>
              </div>
              <div class="w-full bg-gray-200 dark:bg-gray-700 rounded-full h-2.5">
                <div class="bg-blue-600 h-2.5 rounded-full progress-bar" style="width: 65%"></div>
              </div>
            </div>
            <div>
              <div class="flex justify-between mb-1">
                <span>Memory</span>
                <span>4.2GB/8GB</span>
              </div>
              <div class="w-full bg-gray-200 dark:bg-gray-700 rounded-full h-2.5">
                <div class="bg-purple-600 h-2.5 rounded-full progress-bar" style="width: 52.5%"></div>
              </div>
            </div>
            <div>
              <div class="flex justify-between mb-1">
                <span>Network</span>
                <span>5.3MB/s</span>
              </div>
              <div class="w-full bg-gray-200 dark:bg-gray-700 rounded-full h-2.5">
                <div class="bg-green-600 h-2.5 rounded-full progress-bar" style="width: 42%"></div>
              </div>
            </div>
          </div>
        </div>
      </div>
      
      <!-- Updates Card -->
      <div class="card bg-white dark:bg-gray-800 rounded-xl p-6 shadow-lg">
        <h2 class="text-xl font-semibold mb-4">Recent Updates</h2>
        <div class="space-y-3">
          <div class="bg-gray-50 dark:bg-gray-700 p-3 rounded-lg">
            <div class="flex justify-between items-start">
              <span class="text-sm font-medium">Version 2.1.0</span>
              <span class="text-xs text-gray-500">2 hours ago</span>
            </div>
            <p class="text-sm mt-1">Updated server plugins and improved stability</p>
          </div>
          <div class="bg-gray-50 dark:bg-gray-700 p-3 rounded-lg">
            <div class="flex justify-between items-start">
              <span class="text-sm font-medium">Daily Backup</span>
              <span class="text-xs text-gray-500">6 hours ago</span>
            </div>
            <p class="text-sm mt-1">Completed automated server backup</p>
          </div>
          <div class="bg-gray-50 dark:bg-gray-700 p-3 rounded-lg">
            <div class="flex justify-between items-start">
              <span class="text-sm font-medium">New Mode</span>
              <span class="text-xs text-gray-500">1 day ago</span>
            </div>
            <p class="text-sm mt-1">Added survival game mode to server</p>
          </div>
        </div>
        <button class="w-full mt-4 bg-blue-600 hover:bg-blue-700 text-white py-2 px-4 rounded-lg transition">
          View All Updates
        </button>
      </div>
    </div>
    
    <!-- Social Links Section -->
    <div class="card bg-white dark:bg-gray-800 rounded-xl p-6 shadow-lg mb-8">
      <h2 class="text-xl font-semibold mb-4">Connect With Us</h2>
      <div class="grid grid-cols-2 md:grid-cols-3 gap-4">
        <a href="https://www.youtube.com/@Turboig" class="social-card flex flex-col items-center justify-center p-4 bg-gray-50 dark:bg-gray-700 rounded-lg hover:bg-gray-100 dark:hover:bg-gray-600 transition">
          <img src="https://storage.googleapis.com/workspace-0f70711f-8b4e-4d94-86f1-2a93ccde5887/image/725e0995-ba9a-40bb-bd14-fc99b2d68886.png" alt="YouTube logo icon with red background" class="social-icon w-12 h-12 mb-2">
          <span class="font-medium">YouTube</span>
        </a>
        <a href="https://discord.gg/2EDfyR7X" class="social-card flex flex-col items-center justify-center p-4 bg-gray-50 dark:bg-gray-700 rounded-lg hover:bg-gray-100 dark:hover:bg-gray-600 transition">
          <img src="https://storage.googleapis.com/workspace-0f70711f-8b4e-4d94-86f1-2a93ccde5887/image/06b40c9b-1dad-4251-a4c3-00317191966c.png" alt="Discord logo icon with purple background" class="social-icon w-12 h-12 mb-2">
          <span class="font-medium">Discord</span>
        </a>
        <a href="https://t.me/turboig" class="social-card flex flex-col items-center justify-center p-4 bg-gray-50 dark:bg-gray-700 rounded-lg hover:bg-gray-100 dark:hover:bg-gray-600 transition">
          <img src="https://storage.googleapis.com/workspace-0f70711f-8b4e-4d94-86f1-2a93ccde5887/image/cad36edb-e9b4-47b6-adfa-8ffdd1621132.png" alt="Telegram logo icon with blue background" class="social-icon w-12 h-12 mb-2">
          <span class="font-medium">Telegram</span>
        </a>
      </div>
    </div>
    
    <!-- Live Stats Section -->
    <div class="card bg-white dark:bg-gray-800 rounded-xl p-6 shadow-lg">
      <h2 class="text-xl font-semibold mb-4">Live Statistics</h2>
      <div class="grid grid-cols-1 md:grid-cols-3 gap-4">
        <div class="stat-card bg-blue-50 dark:bg-blue-900/20 p-4 rounded-lg">
          <div class="flex items-center justify-between">
            <div>
              <p class="text-sm text-gray-600 dark:text-gray-300">Current Players</p>
              <h3 class="text-2xl font-bold">24</h3>
            </div>
            <div class="bg-blue-100 dark:bg-blue-800/50 p-3 rounded-full">
              <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-blue-600 dark:text-blue-300" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 4.354a4 4 0 110 5.292M15 21H3v-1a6 6 0 0112 0v1zm0 0h6v-1a6 6 0 00-9-5.197M13 7a4 4 0 11-8 0 4 4 0 018 0z" />
              </svg>
            </div>
          </div>
          <div class="mt-2">
            <p class="text-sm text-blue-600 dark:text-blue-300 flex items-center">
              <svg xmlns="http://www.w3.org/2000/svg" class="h-4 w-4" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 10l7-7m0 0l7 7m-7-7v18" />
              </svg>
              <span class="ml-1">3.2% from yesterday</span>
            </p>
          </div>
        </div>
        
        <div class="stat-card bg-green-50 dark:bg-green-900/20 p-4 rounded-lg">
          <div class="flex items-center justify-between">
            <div>
              <p class="text-sm text-gray-600 dark:text-gray-300">Peak Today</p>
              <h3 class="text-2xl font-bold">37</h3>
            </div>
            <div class="bg-green-100 dark:bg-green-800/50 p-3 rounded-full">
              <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-green-600 dark:text-green-300" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 7h8m0 0v8m0-8l-8 8-4-4-6 6" />
              </svg>
            </div>
          </div>
          <div class="mt-2">
            <p class="text-sm text-green-600 dark:text-green-300 flex items-center">
              <svg xmlns="http://www.w3.org/2000/svg" class="h-4 w-4" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 10l7-7m0 0l7 7m-7-7v18" />
              </svg>
              <span class="ml-1">5.7% from yesterday</span>
            </p>
          </div>
        </div>
        
        <div class="stat-card bg-purple-50 dark:bg-purple-900/20 p-4 rounded-lg">
          <div class="flex items-center justify-between">
            <div>
              <p class="text-sm text-gray-600 dark:text-gray-300">New Players</p>
              <h3 class="text-2xl font-bold">12</h3>
            </div>
            <div class="bg-purple-100 dark:bg-purple-800/50 p-3 rounded-full">
              <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-purple-600 dark:text-purple-300" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M18 9v3m0 0v3m0-3h3m-3 0h-3m-2-5a4 4 0 11-8 0 4 4 0 018 0zM3 20a6 6 0 0112 0v1H3v-1z" />
              </svg>
            </div>
          </div>
          <div class="mt-2">
            <p class="
](https://github.com/gamerffa3/turboweb.git)
