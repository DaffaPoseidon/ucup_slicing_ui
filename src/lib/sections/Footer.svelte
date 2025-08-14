<!-- Footer component -->
<script lang="ts">
  import { BookOpen } from 'lucide-svelte';
</script>

<footer class="bg-gray-900 border-t border-gray-800 py-12">
  <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
    <div class="grid grid-cols-1 md:grid-cols-4 gap-8">
      <div>
        <div class="flex items-center mb-4">
          <BookOpen class="h-8 w-8 text-purple-500" />
          <span class="ml-2 text-xl font-bold text-white">NovelHit</span>
        </div>
        <p class="text-gray-400 text-sm">
          Discover, read, and share original stories from talented writers around the world.
        </p>
      </div>
      <div>
        <h4 class="text-white font-semibold mb-4">Explore</h4>
        <ul class="space-y-2 text-sm text-gray-400">
          <li><a href="#" class="hover:text-purple-400">Browse Stories</a></li>
          <li><a href="#" class="hover:text-purple-400">Trending</a></li>
          <li><a href="#" class="hover:text-purple-400">New Releases</a></li>
          <li><a href="#" class="hover:text-purple-400">Editor's Picks</a></li>
        </ul>
      </div>
      <div>
        <h4 class="text-white font-semibold mb-4">Community</h4>
        <ul class="space-y-2 text-sm text-gray-400">
          <li><a href="#" class="hover:text-purple-400">Forums</a></li>
          <li><a href="#" class="hover:text-purple-400">Writing Contest</a></li>
          <li><a href="#" class="hover:text-purple-400">Author Program</a></li>
          <li><a href="#" class="hover:text-purple-400">Support</a></li>
        </ul>
      </div>
      <div>
        <h4 class="text-white font-semibold mb-4">Resources</h4>
        <ul class="space-y-2 text-sm text-gray-400">
          <li><a href="#" class="hover:text-purple-400">Writing Guidelines</a></li>
          <li><a href="#" class="hover:text-purple-400">Help Center</a></li>
          <li><a href="#" class="hover:text-purple-400">Terms of Service</a></li>
          <li><a href="#" class="hover:text-purple-400">Privacy Policy</a></li>
        </ul>
      </div>
    </div>
    <div class="mt-12 pt-8 border-t border-gray-800 text-center">
      <p class="text-gray-400 text-sm">
        © 2024 NovelHit. All rights reserved.
      </p>
    </div>
  </div>
</footer>
