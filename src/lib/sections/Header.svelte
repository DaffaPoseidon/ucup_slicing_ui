<script lang="ts">
  import { Search, BookOpen, User, Menu, X, Bell } from 'lucide-svelte';
  import Button from '$lib/components/Button.svelte';
  
  let isMobileMenuOpen = false;
  
  function toggleMobileMenu() {
    isMobileMenuOpen = !isMobileMenuOpen;
  }
  
  function closeMobileMenu() {
    isMobileMenuOpen = false;
  }
</script>

<header class="bg-gray-900 py-4 border-b border-gray-800 relative">
  <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
    <div class="flex justify-between items-center">
      
      <!-- Mobile Layout (< 600px) -->
      <div class="flex items-center justify-between w-full max-[600px]:flex min-[600px]:hidden">
        <!-- Logo -->
        <div class="flex items-center space-x-2">
          <BookOpen class="h-8 w-8 text-purple-500" />
          <span class="text-white font-bold text-xl">NH</span>
        </div>
        
        <!-- Mobile actions -->
        <div class="flex items-center space-x-3">
          <!-- Search Bar -->
          <div class="relative">
            <Search class="absolute left-3 top-1/2 transform -translate-y-1/2 h-4 w-4 text-gray-400" />
            <input 
              type="text" 
              placeholder="Search..." 
              class="bg-gray-800 text-white pl-10 pr-4 py-2 rounded-lg focus:outline-none focus:ring-1 focus:ring-purple-500 border border-gray-700 w-full text-sm"
            />
          </div>
          
          <!-- Notification Bell -->
          <button class="relative p-2 text-gray-300 hover:text-white transition-colors">
            <Bell class="h-5 w-5" />
            <span class="absolute -top-1 -right-1 h-3 w-3 bg-red-500 rounded-full animate-pulse"></span>
          </button>
          
          <!-- Profile Icon -->
          <button class="flex items-center justify-center w-8 h-8 rounded-full bg-purple-600 hover:bg-purple-700 transition-colors">
            <User class="h-4 w-4 text-white" />
          </button>
          
          <!-- Hamburger Menu -->
          <button 
            on:click={toggleMobileMenu}
            class="p-2 text-gray-300 hover:text-white transition-colors"
            aria-label="Toggle mobile menu"
          >
            <Menu class="h-6 w-6" />
          </button>
        </div>
      </div>

      <!-- Desktop Layout (>= 600px) -->
      <div class="min-[600px]:flex justify-between items-center w-full max-[600px]:hidden">
        <!-- Logo and nav -->
        <div class="flex items-center">
          <div class="flex items-center space-x-2">
            <BookOpen class="h-8 w-8 text-purple-500" />
            <span class="text-white font-bold text-xl">NH</span>
          </div>
          <nav class="hidden md:flex ml-10 space-x-6">
            <a href="/#" class="text-white hover:text-purple-400">Browse</a>
            <a href="/#" class="text-gray-300 hover:text-purple-400">Rankings</a>
            <a href="/#" class="text-gray-300 hover:text-purple-400">New</a>
            <a href="/#" class="text-gray-300 hover:text-purple-400">Genres</a>
            <a href="/#" class="text-gray-300 hover:text-purple-400">Authors</a>
          </nav>
        </div>
        
        <!-- Search and actions -->
        <div class="flex items-center space-x-4">
          <div class="relative">
            <Search class="absolute left-3 top-1/2 transform -translate-y-1/2 h-5 w-5 text-gray-400" />
            <input 
              type="text" 
              placeholder="Search stories..." 
              class="bg-gray-800 text-white pl-10 pr-4 py-2 rounded-lg focus:outline-none focus:ring-1 focus:ring-purple-500 border border-gray-700"
            />
          </div>
          <Button variant="primary">Write</Button>
          <div class="flex items-center justify-center w-8 h-8 rounded-full bg-purple-600">
            <User class="h-5 w-5 text-white" />
          </div>
        </div>
      </div>
    </div>
  </div>

  <!-- Mobile Sidebar Menu -->
  {#if isMobileMenuOpen}
    <!-- Overlay -->
    <div 
      class="fixed inset-0 bg-black bg-opacity-50 z-40 max-[600px]:block min-[600px]:hidden"
      on:click={closeMobileMenu}
      on:keydown={(e) => e.key === 'Escape' && closeMobileMenu()}
      role="button"
      tabindex="0"
      aria-label="Close mobile menu"
    ></div>
    
    <!-- Sidebar -->
    <div class="fixed top-0 left-0 h-full w-80 bg-gray-900 border-r border-gray-800 z-50 transform transition-transform duration-300 ease-in-out max-[600px]:block min-[600px]:hidden overflow-auto [&::-webkit-scrollbar]:w-1 [&::-webkit-scrollbar-track]:bg-gray-700 [&::-webkit-scrollbar-thumb]:bg-gray-500 [&::-webkit-scrollbar-thumb]:rounded [&::-webkit-scrollbar-thumb:hover]:bg-gray-400">
      <!-- Header -->
      <div class="flex items-center justify-between p-4 border-b border-gray-800">
        <div class="flex items-center space-x-2">
          <BookOpen class="h-8 w-8 text-purple-500" />
          <span class="text-white font-bold text-xl">Novel Hub</span>
        </div>
        <button 
          on:click={closeMobileMenu}
          class="p-2 text-gray-300 hover:text-white"
          aria-label="Close mobile menu"
        >
          <X class="h-6 w-6" />
        </button>
      </div>
      
      <!-- Navigation Links -->
      <nav class="p-4 space-y-4">
        <a 
          href="/browse" 
          class="block text-white hover:text-purple-400 py-3 px-4 rounded-lg hover:bg-gray-800 transition-colors"
          on:click={closeMobileMenu}
        >
          Browse
        </a>
        <a 
          href="/trending" 
          class="block text-gray-300 hover:text-purple-400 py-3 px-4 rounded-lg hover:bg-gray-800 transition-colors"
          on:click={closeMobileMenu}
        >
          Trending
        </a>
        <a 
          href="/library" 
          class="block text-gray-300 hover:text-purple-400 py-3 px-4 rounded-lg hover:bg-gray-800 transition-colors"
          on:click={closeMobileMenu}
        >
          Library
        </a>
        <a 
          href="/contest" 
          class="block text-gray-300 hover:text-purple-400 py-3 px-4 rounded-lg hover:bg-gray-800 transition-colors"
          on:click={closeMobileMenu}
        >
          Contest
        </a>
      </nav>
      
      <!-- Write Button -->
      <div class="p-4 border-t border-gray-800 mt-auto">
        <Button variant="primary" className="w-full">Write Story</Button>
      </div>
    </div>
  {/if}
</header>
