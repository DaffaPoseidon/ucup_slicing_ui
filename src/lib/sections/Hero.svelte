<!-- Hero section component -->
<script lang="ts">
  import Button from '$lib/components/Button.svelte';
  import { Book, Star } from 'lucide-svelte';
</script>

<section class="bg-gray-900 py-20">
  <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
    <div class="flex flex-col lg:flex-row items-center">
      <div class="lg:w-1/2 lg:pr-10">
        <h1 class="text-4xl lg:text-5xl font-bold text-white mb-6">
          Discover Original Stories from Talented Writers
        </h1>
        <p class="text-gray-300 text-lg mb-8">
          Embark on a journey through thousands of original stories across every genre. Find your next favorite read or share your own creations.
        </p>
        <div class="flex flex-col sm:flex-row space-y-4 sm:space-y-0 sm:space-x-4">
          <Button variant="primary" className="px-6 py-3 text-base font-medium">
            Start Reading
          </Button>
          <Button variant="secondary" className="px-6 py-3 text-base font-medium">
            Publish Your Story
          </Button>
        </div>
      </div>
      
      <div class="lg:w-1/2 mt-10 lg:mt-0">
        <div class="bg-gray-800 p-6 rounded-xl border border-gray-700 max-w-md mx-auto">
          <div class="flex items-center mb-4">
            <div class="flex-shrink-0">
              <Book class="h-12 w-12 text-purple-500" />
            </div>
            <div class="ml-4">
              <h3 class="text-xl font-semibold text-white">The Last Magician</h3>
              <div class="flex items-center mt-1">
                <Star class="h-4 w-4 text-yellow-400 fill-current" />
                <Star class="h-4 w-4 text-yellow-400 fill-current" />
                <Star class="h-4 w-4 text-yellow-400 fill-current" />
                <Star class="h-4 w-4 text-yellow-400 fill-current" />
                <Star class="h-4 w-4 text-yellow-400 fill-current" />
                <span class="ml-2 text-sm text-gray-400">4.9 (356 reviews)</span>
              </div>
            </div>
          </div>
          
          <p class="text-gray-300 mb-4">
            When Alex discovers an ancient spell book, he's pulled into a hidden world of magic that has existed alongside our own for centuries. But dark forces are gathering, and he may be the only one who can stop them.
          </p>
          
          <div class="flex items-center justify-between text-sm text-gray-400">
            <span>Fantasy • 45 Chapters</span>
            <span>By Sarah Chen</span>
          </div>
          
          <Button variant="primary" className="w-full mt-4 py-2">
            Read Now
          </Button>
        </div>
      </div>
    </div>
  </div>
</section>
