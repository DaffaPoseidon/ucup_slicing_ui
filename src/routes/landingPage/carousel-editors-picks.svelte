<script lang="ts">
  import { BookOpen } from 'lucide-svelte';
  
  const editorsPicks = [
    { title: 'The Last Magician', author: 'Alexandra Stone', genre: ['Fantasy'], rating: 4.8 },
    { title: 'Crimson Empire', author: 'Victoria Cross', genre: ['Fantasy'], rating: 4.9 },
    { title: 'Chronicles of the Forgotten', author: 'Thomas Grey', genre: ['Adventure', 'Romance'], rating: 4.7 },
    { title: 'Shadows Convergence', author: 'Amanda White', genre: ['Mystery'], rating: 4.6 }
  ];
</script>

<!-- Editor's Picks Section -->
<section class="py-20 bg-[#020917]">
  <div class="max-w-full mx-auto px-4 sm:px-6 lg:px-8">
    <div class="flex items-center justify-between mb-8">
      <div class="flex items-center gap-3">
        <svg class="h-6 w-6 text-[#9260FE]" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4M7.835 4.697a3.42 3.42 0 001.946-.806 3.42 3.42 0 014.438 0 3.42 3.42 0 001.946.806 3.42 3.42 0 013.138 3.138 3.42 3.42 0 00.806 1.946 3.42 3.42 0 010 4.438 3.42 3.42 0 00-.806 1.946 3.42 3.42 0 01-3.138 3.138 3.42 3.42 0 00-1.946.806 3.42 3.42 0 01-4.438 0 3.42 3.42 0 00-1.946-.806 3.42 3.42 0 01-3.138-3.138 3.42 3.42 0 00-.806-1.946 3.42 3.42 0 010-4.438 3.42 3.42 0 00.806-1.946 3.42 3.42 0 013.138-3.138z" />
        </svg>
        <h2 class="text-2xl font-bold text-white">Editor's Picks</h2>
      </div>
      <a href="/" class="text-[#9260FE] hover:text-purple-300">View All →</a>
    </div>
    <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-4 gap-6">
      {#each editorsPicks as book}
        <div class="bg-[#121827] rounded-xl overflow-hidden border border-gray-700 hover:border-primary-500 transition-colors hover:scale-105 duration-300">
          <div class="bg-gray-700 h-72 flex items-center justify-center relative">
            <span class="absolute top-[1em] right-[1em] bg-[#EF4344] text-white text-xs px-2 py-1 rounded-[1em] font-bold flex items-center gap-1">
              <svg class="h-3 w-3" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17.657 18.657A8 8 0 016.343 7.343S7 9 9 10c0-2 .5-5 2.986-7C14 5 16.09 5.777 17.656 7.343A7.975 7.975 0 0120 13a7.975 7.975 0 01-2.343 5.657z" />
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9.879 16.121A3 3 0 1012.015 11L11 14H9c0 .768.293 1.536.879 2.121z" />
              </svg>
              Hot
            </span>
            <BookOpen class="h-12 w-12 text-white/30" />
          </div>
          <div class="flex flex-col flex-wrap justify-start p-[1em]">
            <h3 class="text-white font-semibold mb-1">{book.title}</h3>
            <p class="text-gray-400 text-sm mb-3">by {book.author}</p>
            
            <!-- Rating -->
            <div class="flex gap-4 items-center mb-3">
              <div class="flex items-center">
                <svg class="h-4 w-4 text-yellow-400 fill-current mr-1" viewBox="0 0 20 20">
                  <path d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z" />
                </svg>
                <span class="text-gray-400 text-xs">{book.rating}</span>
              </div>
            </div>
            
            <!-- Genre and Status -->
            <div class="flex flex-wrap gap-[1em]">
              <!-- Genre -->
              <div class="flex flex-wrap gap-[1em]">
                {#each book.genre as g}
                  <span class="bg-[#1F2A3B] text-gray-300 text-xs px-3 py-1 rounded-full border border-gray-700/10">
                    {g}
                  </span>
                {/each}
              </div>
              
              <!-- Status - Alternating between Ongoing and Completed -->
              <div>
                {#if book.title.length % 2 === 0}
                  <span class="bg-transparent text-[#23C55E] text-xs px-3 py-1 rounded-full border border-[#23C55E]">
                    Completed
                  </span>
                {:else}
                  <span class="bg-transparent text-[#3676E0] text-xs px-3 py-1 rounded-full border border-[#3676E0]">
                    Ongoing
                  </span>
                {/if}
              </div>
            </div>
          </div>
        </div>
      {/each}
    </div>
  </div>
</section>
