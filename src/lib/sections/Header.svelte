<script lang="ts">
  import { Search, BookOpen, User, Menu, X, Bell, Crown } from 'lucide-svelte';
  import Button from '$lib/components/Button.svelte';
  
  let isMobileMenuOpen = false;
  let isSearchOpen = false;
  let canShowSearchButton = true; // controls when the mobile search icon is visible after animations
  let notificationCount = 3; // Number of notifications
  
  function toggleMobileMenu() {
    isMobileMenuOpen = !isMobileMenuOpen;
  }
  
  function closeMobileMenu() {
    isMobileMenuOpen = false;
  }
  
  function toggleSearch() {
    isSearchOpen = !isSearchOpen;
  }
</script>


<header class="bg-[#020917] border-b border-gray-800 flex items-center justify-between px-[4vw] py-[2vw] w-[100%]">
  <!-- Div 1: Logo, Title, Nav (menu) -->
  <div class="flex items-center justify-between gap-[2em]">
    <div class="flex items-center gap-[1em]">
      <BookOpen class="h-8 w-8 text-[#9260FE]"/>
      <span class="text-white font-bold text-xl">NH</span>
    </div>
    <nav class="flex-1 min-w-0 max-[600px]:hidden">
      <div class="flex gap-[1em] flex-wrap">
        <a href="/#" class="text-white hover:text-purple-400 whitespace-nowrap">Browse</a>
        <a href="/#" class="text-gray-300 hover:text-purple-400 whitespace-nowrap">Rankings</a>
        <a href="/#" class="text-gray-300 hover:text-purple-400 whitespace-nowrap">New</a>
        <a href="/#" class="text-gray-300 hover:text-purple-400 whitespace-nowrap">Genres</a>
        <a href="/#" class="text-gray-300 hover:text-purple-400 whitespace-nowrap">Authors</a>
      </div>
    </nav>
  </div>

  <!-- Div 2: Search, Write, Notification, Profile, Hamburger -->
  <div class="flex items-center gap-[1em]">
    <!-- Search (desktop) -->
    <div class="hidden min-[600px]:flex items-center bg-gray-800 rounded-lg gap-2 px-2">
      <Search class="h-5 w-5 text-gray-400" />
        <input 
          type="text" 
          placeholder="Search stories..." 
          class="bg-gray-800 text-white py-2 px-2 rounded-lg focus:outline-none focus:ring-1 focus:ring-purple-500 border border-gray-700 w-[12vw] min-w-[100px] max-w-[220px]"
        />
    </div>
    <!-- Search (mobile) -->
    <div class="flex min-[600px]:hidden items-center gap-0">

      <div
        class="flex items-center bg-gray-800 rounded-lg gap-1 px-2 transition-all duration-300 ease-in-out"
        style="width: {isSearchOpen ? 'clamp(38vw,30vw,38vw)' : '0'}; opacity: {isSearchOpen ? 1 : 0}; pointer-events: {isSearchOpen ? 'auto' : 'none'}; overflow: hidden; transition-property: width,opacity;"
        on:transitionend={() => { if (!isSearchOpen) canShowSearchButton = true; }}
      >
        <input
          type="text"
          placeholder="Search..."
          class="bg-gray-800 text-white py-2 px-2 rounded-lg focus:outline-none focus:ring-0 border-0 w-full text-sm"
        />
        <button
          on:click={() => { isSearchOpen = false; }}
          class="p-2 text-gray-300 hover:text-white transition-colors"
        >
          <X class="h-4 w-4" />
        </button>
      </div>
            {#if canShowSearchButton}
        <button
          on:click={() => { canShowSearchButton = false; isSearchOpen = true; }}
          class="text-gray-300 hover:text-white transition-colors"
        >
          <Search class="h-5 w-5" />
        </button>
      {/if}
    </div>
    <!-- Write Button (desktop only) -->
    <div class="hidden min-[600px]:block">
      <Button variant="primary">Write</Button>
    </div>
    <!-- Notification Bell -->
    <div class="flex items-center">
      <button class="p-2 text-gray-300 hover:text-white transition-colors">
        <span class="grid grid-cols-1 grid-rows-1 place-items-center">
          <Bell class="h-6 w-6 col-start-1 row-start-1" />
          <span class="col-start-1 row-start-1 justify-self-end self-start translate-x-[30%] -translate-y-[50%] flex items-center justify-center min-w-[1.2em] h-[1.2em] px-[0.3em] bg-red-500 rounded-full text-white text-xs font-bold">{notificationCount}</span>
        </span>
      </button>
    </div>
    <!-- Profile Icon with Crown -->
    <div class="flex items-center">
      <div class="flex items-center justify-center w-8 h-8 rounded-full bg-purple-600 hover:bg-purple-700 transition-colors relative">
        <User class="h-5 w-5 text-white" />
        <span class="flex items-center justify-center w-4 h-4 bg-yellow-500 rounded-full absolute right-[-0.5em] top-[-0.5em]">
          <Crown class="h-3 w-3 text-yellow-900" />
        </span>
      </div>
    </div>
    <!-- Hamburger Menu (mobile only) -->
    <button 
      on:click={toggleMobileMenu}
      class="p-2 text-gray-300 hover:text-white transition-colors min-[600px]:hidden"
      aria-label="Toggle mobile menu"
    >
      <Menu class="h-6 w-6" />
    </button>
  </div>

  <!-- Mobile Sidebar Menu -->
  <!-- Overlay with semi-transparent background -->
  <div 
    class="fixed inset-0 bg-black bg-opacity-50 z-40 transition-opacity duration-300 ease-in-out max-[880px]:block min-[880px]:hidden {isMobileMenuOpen ? 'opacity-100' : 'opacity-0 pointer-events-none'}"
    on:click={closeMobileMenu}
    on:keydown={(e) => e.key === 'Escape' && closeMobileMenu()}
    role="button"
    tabindex="0"
    aria-label="Close mobile menu"
  ></div>
  
  <!-- Sidebar with smooth slide-in animation -->
  <div class="fixed top-0 left-0 h-full w-80 bg-[#020917] border-r border-gray-800 z-50 transform transition-transform duration-300 ease-in-out max-[880px]:block min-[880px]:hidden overflow-auto [&::-webkit-scrollbar]:w-1 [&::-webkit-scrollbar-track]:bg-gray-700 [&::-webkit-scrollbar-thumb]:bg-gray-500 [&::-webkit-scrollbar-thumb]:rounded [&::-webkit-scrollbar-thumb:hover]:bg-gray-400 {isMobileMenuOpen ? 'translate-x-0' : '-translate-x-full'}">
    <!-- Header -->
    <div class="flex items-center justify-between p-4 border-b border-gray-800">
      <div class="flex items-center space-x-2">
        <BookOpen class="h-8 w-8 text-[#9260FE]" />
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
</header>
