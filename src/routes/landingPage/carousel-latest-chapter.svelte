<script lang="ts">
  import { BookOpen, Clock } from 'lucide-svelte';
  
  // Latest chapter data
  const latestChapters = [
    { title: 'The Last Magician', chapter: 46, chapterTitle: 'The Forgotten Tower', timeAgo: '2 hours ago', author: 'Elena Rivers' },
    { title: 'Shadow of Tomorrow', chapter: 33, chapterTitle: 'Time Paradox', timeAgo: '4 hours ago', author: 'Marcus Chen' },
    { title: 'Memories of the Past', chapter: 29, chapterTitle: 'Lost Fragments', timeAgo: '6 hours ago', author: 'Sarah Miller' },
    { title: 'The Alchemist\'s Legacy', chapter: 41, chapterTitle: 'Secrets of Fire', timeAgo: '8 hours ago', author: 'Robert Johnson' },
    { title: 'City of Dragons', chapter: 52, chapterTitle: 'Dragon\'s Awakening', timeAgo: '12 hours ago', author: 'Liam Wang' }
  ];
</script>

<!-- Latest Chapters Section -->
<section class="py-20">
  <div class="max-w-full mx-auto px-4 sm:px-6 lg:px-8">
    <div class="flex items-center justify-between mb-8">
      <h2 class="text-2xl font-bold text-white">Latest Chapter Updates</h2>
      <a href="#" class="text-[#9260FE] hover:text-purple-300">View All →</a>
    </div>
    <div class="grid grid-cols-1 md:grid-cols-5 gap-6">
      {#each latestChapters as chapter}
        <div class="bg-gray-800 rounded-xl overflow-hidden border border-gray-700 hover:border-purple-500 transition-colors">
          <div class="bg-gray-700 h-[40vh] relative">
            <!-- Background image - using a placeholder since we don't have actual images -->
            <div class="absolute inset-0 bg-gradient-to-t from-gray-900 to-transparent z-10"></div>
            <div class="w-full h-full bg-center bg-cover" style="background-image: url('https://source.unsplash.com/random/300x400?book'); background-position: center;"></div>
            
            <!-- Chapter info at bottom left -->
            <div class="absolute bottom-3 left-3 z-20">
              <h3 class="text-white font-semibold text-sm leading-tight">
                Chapter {chapter.chapter}: {chapter.chapterTitle}
              </h3>
              <p class="text-gray-300 text-xs mt-1">{chapter.timeAgo}</p>
            </div>
          </div>
          <div class="flex flex-col flex-wrap justify-start p-[1em]">
            <h4 class="text-white font-medium text-sm mb-1">{chapter.title}</h4>
            <p class="text-gray-400 text-xs mb-2">by {chapter.author}</p>
            <a href="#" class="text-[#9260FE] hover:text-purple-300 text-xs font-medium">Read Now &gt;</a>
          </div>
        </div>
      {/each}
    </div>
  </div>
</section>
