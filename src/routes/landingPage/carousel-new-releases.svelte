<script lang="ts">
  import { BookOpen, Clock } from 'lucide-svelte';
  
  // Dummy data for new releases
  const newReleases = [
    { title: 'Whispers in the Dark', author: 'Sarah Miller', genre: ['Horror', 'Romance'], rating: 4.5, chapters: 24, status: 'Ongoing' },
    { title: 'The Alchemist\'s Daughter', author: 'Robert Johnson', genre: ['Fantasy'], rating: 4.7, chapters: 36, status: 'Completed' },
    { title: 'Midnight Serenade', author: 'Lisa Wang', genre: ['Romance'], rating: 4.6, chapters: 18, status: 'Ongoing' },
    { title: 'Chronicles Blue', author: 'Michael Brown', genre: ['Adventure'], rating: 4.4, chapters: 42, status: 'Ongoing' }
  ];
  
</script>

<!-- New Releases -->
<section class="py-20 bg-[#020917]">
  <div class="max-w-full mx-auto px-4 sm:px-6 lg:px-8">
    <div class="flex items-center justify-between mb-8">
      <div class="flex items-center gap-3">
        <BookOpen class="h-6 w-6 text-[#9260FE]"/>
        <h2 class="text-2xl font-bold text-white">New Releases</h2>
      </div>
      <a href="#" class="text-[#9260FE] hover:text-purple-300">View All →</a>
    </div>
    <div class="grid grid-cols-2 md:grid-cols-4 gap-6">
      {#each newReleases as book}
        <div class="bg-[#121827] rounded-xl overflow-hidden border border-gray-700 hover:border-primary-500 transition-colors">
          <div class="bg-gray-700 h-72 flex relative">
            <span class="absolute top-[1em] left-[1em] bg-[#23C55E] text-white text-xs px-2 py-1 rounded-[1em] font-bold">
              New
            </span>
            <img src="" alt="">
          </div>
          <div class="flex flex-col flex-wrap justify-start p-[1em]">
            <h3 class="text-white font-semibold mb-1">{book.title}</h3>
            <p class="text-gray-400 text-sm mb-3">by {book.author}</p>
            
            <!-- Rating and Chapters -->
            <div class="flex gap-4 items-center mb-3">
              <!-- Rating -->
              <div class="flex items-center">
                <svg class="h-4 w-4 text-yellow-400 fill-current mr-1" viewBox="0 0 20 20">
                  <path d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z" />
                </svg>
                <span class="text-gray-400 text-xs">{book.rating}</span>
              </div>
              
              <!-- Chapters -->
              <div class="flex items-center">
                <BookOpen class="h-4 w-4 text-gray-500 mr-1"/>
                <span class="text-gray-500 text-xs">{book.chapters} chapters</span>
              </div>
            </div>
            
            <!-- Genre and Status -->
            <div class="flex gap-[1em] flex-wrap items-center">
              <!-- Genre -->
              <div class="flex gap-[1em]">
  {#each Array.isArray(book.genre) ? book.genre : [book.genre] as g}
    <span class="bg-[#1F2A3B] text-gray-300 text-xs px-3 py-1 rounded-full border border-gray-700/10">
      {g}
    </span>
  {/each}
              </div>
              
              <!-- Status -->
              <div>
                <span class="bg-transparent text-{book.status === 'Completed' ? '[#23C55E]' : '[#3676E0]'} text-xs px-3 py-1 rounded-full border border-{book.status === 'Completed' ? '[#23C55E]' : '[#3676E0]'}">
                  {book.status}
                </span>
              </div>
            </div>
          </div>
        </div>
      {/each}
    </div>
  </div>
</section>
