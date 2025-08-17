<script lang="ts">
  import Button from '$lib/components/Button.svelte';
    import { BookOpen, Star, Flame, Bookmark, Eye, Globe, Pen, Users } from 'lucide-svelte';

  // Variables for stats
  let rating = 4.8;
  let chapters = 142;
  let readers = "1.2M";
  let reviews = 356;
</script>

<section class="bg-gray-900 py-20">
  <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
    <div class="flex flex-col lg:flex-row items-center">
      <div class="lg:w-1/2 lg:pr-10">
        <div class="inline-flex items-center px-3 py-1.5 bg-[#212041] rounded-[1em] mb-4">
          <Flame class="h-4 w-4 text-[#8A5FFD]" />
          <span class="ml-2 text-xs font-bold text-[#8A5FFD]">Featured Story</span>
        </div>
        <h1 class="text-4xl lg:text-5xl font-bold text-white mb-6">
          Discover Original Stories
        </h1>
        <p class="text-gray-300 text-lg mb-8">
          Embark on a journey through thousands of original stories across every genre. Find your next favorite read or share your own creations.
        </p>
        <div class="flex flex-row space-x-4">
          <Button variant="primary" className="px-[2em] py-[0.5em] text-base font-medium flex items-center">
            Start Reading
            <BookOpen class="h-4 w-4 ml-2" />
          </Button>
          <Button variant="secondary" className="bg-[#020917] border border-[#8A5FFD] text-white hover:bg-[#8A5FFD] hover:text-white px-[2em] py-[0.5em] text-base font-medium">
            Explore More &gt;
          </Button>
        </div>
        <div class="flex items-center gap-[1em] mt-6 text-base font-medium">
          <div class="flex items-center">
            <Star class="h-5 w-5 text-yellow-400 fill-current mr-2" />
            <span><strong>{rating}</strong> rating</span>
          </div>
          <div class="flex items-center">
            <Bookmark class="h-5 w-5 text-purple-400 mr-2" />
            <span><strong>{chapters}</strong> Chapters</span>
          </div>
          <div class="flex items-center">
            <Eye class="h-5 w-5 text-blue-400 mr-2" />
            <span><strong>{readers}</strong> Readers</span>
          </div>
        </div>
      </div>      
      <div class="lg:w-1/2 mt-10 lg:mt-0">
        <div class="bg-gray-800 p-6 rounded-xl border border-gray-700 max-w-md mx-auto">
          <div class="flex items-center mb-4">
            <div class="flex-shrink-0">
              <BookOpen class="h-12 w-12 text-purple-500" />
            </div>
            <div class="ml-4">
              <h3 class="text-xl font-semibold text-white">The Last Magician</h3>
              <div class="flex items-center mt-1">
                <Star class="h-4 w-4 text-yellow-400 fill-current" />
                <Star class="h-4 w-4 text-yellow-400 fill-current" />
                <Star class="h-4 w-4 text-yellow-400 fill-current" />
                <Star class="h-4 w-4 text-yellow-400 fill-current" />
                <Star class="h-4 w-4 text-yellow-400 fill-current" />
                <span class="ml-2 text-sm text-gray-400">{rating} ({reviews} reviews)</span>
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

<!-- Statistics Section -->
<section class="py-20 bg-gray-800/50">
  <div class="max-w-full mx-auto px-4 sm:px-6 lg:px-8">
    <div class="grid grid-cols-2 md:grid-cols-4 gap-8">
      <div class="text-center bg-gray-800 p-6 rounded-xl border border-gray-700">
        <div class="flex justify-center mb-4">
          <BookOpen class="h-10 w-10 text-[#9260FE]"/>
        </div>
        <div class="text-3xl font-bold text-white mb-2">50K+</div>
        <div class="text-gray-400">Original Stories</div>
      </div>
      <div class="text-center bg-gray-800 p-6 rounded-xl border border-gray-700">
        <div class="flex justify-center mb-4">
          <Users class="h-10 w-10 text-[#9260FE]"/>
        </div>
        <div class="text-3xl font-bold text-white mb-2">1.2M+</div>
        <div class="text-gray-400">Active Readers</div>
      </div>
      <div class="text-center bg-gray-800 p-6 rounded-xl border border-gray-700">
        <div class="flex justify-center mb-4">
          <Pen class="h-10 w-10 text-[#9260FE]"/>
        </div>
        <div class="text-3xl font-bold text-white mb-2">75K+</div>
        <div class="text-gray-400">Published Authors</div>
      </div>
      <div class="text-center bg-gray-800 p-6 rounded-xl border border-gray-700">
        <div class="flex justify-center mb-4">
          <Globe class="h-10 w-10 text-[#9260FE]"/>
        </div>
        <div class="text-3xl font-bold text-white mb-2">100+</div>
        <div class="text-gray-400">Countries</div>
      </div>
    </div>
  </div>
</section>
