<script lang="ts">
  import { BookOpen } from 'lucide-svelte';

  // Component state
  let selectedGenre = 'All';
  
  const genres = ['Fantasy', 'Sci-Fi', 'Romance', 'All'];
  
  const weeklyRankings = [
    { rank: 1, title: 'Divine Academy', author: 'Sarah Chen', rating: 4.9, genre: 'Fantasy' },
    { rank: 2, title: 'Shadow Hunter', author: 'Mike Ross', rating: 4.7, genre: 'Action' },
    { rank: 3, title: 'Lunar Eclipse', author: 'Anna Smith', rating: 4.5, genre: 'Romance' },
    { rank: 4, title: 'Crimson Empire', author: 'John Doe', rating: 4.3, genre: 'Fantasy' },
    { rank: 5, title: 'Midnight Tales', author: 'Jane Wilson', rating: 4.1, genre: 'Mystery' }
  ];
  
  const trendingBooks = [
    {
      title: 'The Last Magician',
      author: 'Alexandra Stone',
      genre: 'Fantasy',
      rating: 4.8,
      chapters: 45,
      status: 'Hot',
      description: 'A young mage discovers ancient powers that could save or destroy the world.'
    },
    {
      title: 'Echoes of Tomorrow',
      author: 'Marcus Chen',
      genre: 'Sci-Fi',
      rating: 4.7,
      chapters: 32,
      status: 'Hot',
      description: 'Time travel meets romance in this thrilling sci-fi adventure.'
    },
    {
      title: 'Forgotten Realms',
      author: 'Elena Rodriguez',
      genre: ['Adventure', 'Romance'],
      rating: 4.6,
      chapters: 28,
      status: 'New',
      description: 'Explore mystical lands filled with ancient secrets and magic.'
    },
    {
      title: 'Heart of the Storm',
      author: 'David Kim',
      genre: 'Romance',
      rating: 4.9,
      chapters: 38,
      status: 'New',
      description: 'A passionate love story set against the backdrop of war.'
    }
  ];

</script>

<!-- Trending & Rankings Section -->
<section class="py-20 bg-gray-800/30">
  <div class="max-w-full mx-auto px-4 sm:px-6 lg:px-8">
    <div class="grid grid-cols-1 lg:grid-cols-3 gap-12">
      <!-- Trending Now -->
      <div class="lg:col-span-2">
        <div class="flex items-center justify-between mb-8">
          <h2 class="text-2xl font-bold text-white">Trending Now</h2>
          <a href="#" class="text-[#9260FE] hover:text-purple-300">View All →</a>
        </div>
    <div class="grid grid-cols-2 md:grid-cols-4 gap-6">
      {#each trendingBooks as book}
        <div class="bg-[#121827] rounded-xl overflow-hidden border border-gray-700 hover:border-primary-500 transition-colors">
          <div class="bg-gray-700 h-72 flex items-center justify-center relative">
            <span class="absolute top-[1em] right-[1em] bg-[#EF4344] text-white text-xs px-2 py-1 rounded-[1em] font-bold flex items-center gap-1">
              <svg class="h-3 w-3" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17.657 18.657A8 8 0 016.343 7.343S7 9 9 10c0-2 .5-5 2.986-7C14 5 16.09 5.777 17.656 7.343A7.975 7.975 0 0120 13a7.975 7.975 0 01-2.343 5.657z" />
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9.879 16.121A3 3 0 1012.015 11L11 14H9c0 .768.293 1.536.879 2.121z" />
              </svg>
              Hot
            </span>
            <img src="" alt="">
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
  {#each Array.isArray(book.genre) ? book.genre : [book.genre] as g}
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

      <!-- Weekly Rankings -->
      <div>
        <div class="flex items-center justify-between mb-8">
          <h2 class="text-2xl font-bold text-white">Weekly Rankings</h2>
          <a href="#" class="text-[#9260FE] hover:text-primary-300">Full Rankings →</a>
        </div>
        <div class="bg-[#121827] rounded-[1em]">
          <!-- Genre Selector -->
          <div class="p-4 border-b border-gray-700">
            <div class="flex items-center justify-between w-full flex-wrap gap-2 bg-[#1F2A3B] border border-gray-700/10 rounded-[1em] p-2">
              {#each genres as genre}
                <button 
                  class="{selectedGenre === genre 
                    ? 'bg-[#020917] text-white' 
                    : 'text-gray-400 hover:text-gray-200'} 
                    px-4 py-2 rounded-lg transition-colors"
                  on:click={() => selectedGenre = genre}
                >
                  {genre}
                </button>
              {/each}
            </div>
          </div>
          <!-- Rankings List -->
          <div class="p-4">
            <div class="space-y-4">
              {#each weeklyRankings.filter(item => selectedGenre === 'All' || item.genre === selectedGenre) as item}
                <div class="flex items-center space-x-3 p-3 rounded-lg hover:bg-gray-700 transition-colors">
                  <div class="w-8 h-8 bg-purple-600 rounded-full flex items-center justify-center text-sm font-bold text-white">
                    {item.rank}
                  </div>

                  <!-- Book cover image -->
                  <div class="w-12 h-16 bg-gray-700 rounded overflow-hidden flex-shrink-0 flex items-center justify-center">
                    <svg class="h-6 w-6 text-white opacity-50" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 6.253v13m0-13C10.832 5.477 9.246 5 7.5 5S4.168 5.477 3 6.253v13C4.168 18.477 5.754 18 7.5 18s3.332.477 4.5 1.253m0-13C13.168 5.477 14.754 5 16.5 5c1.746 0 3.332.477 4.5 1.253v13C19.832 18.477 18.246 18 16.5 18c-1.746 0-3.332.477-4.5 1.253" />
                    </svg>
                  </div>

                  <div class="flex-1">
                    <p class="text-white font-medium text-sm">{item.title}</p>
                    <p class="text-gray-400 text-xs">by {item.author}</p>
                  </div>
                  
                  <!-- Rating instead of views -->
                  <div class="flex items-center">
                    <svg class="h-4 w-4 text-yellow-400 fill-current mr-1" viewBox="0 0 20 20">
                      <path d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z" />
                    </svg>
                    <span class="text-primary-400 text-xs">{item.rating.toFixed(1)}</span>
                  </div>
                </div>
              {/each}
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>
