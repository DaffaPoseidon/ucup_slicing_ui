<script lang="ts">
  // Genres data
  const genres = ["Romance", "Fantasy", "Mystery", "Sci-Fi", "Horror", "Drama", 
                  "Adventure", "Historical", "Comedy", "Thriller", "Young Adult", "Paranormal"];
</script>

<!-- Browse by Genre Section -->
<section class="py-20 bg-gray-800/30">
  <div class="max-w-full mx-auto px-4 sm:px-6 lg:px-8">
    <div class="flex items-center justify-between mb-8">
      <h2 class="text-2xl font-bold text-white">Browse by Genre</h2>
      <a href="/" class="text-[#9260FE] hover:text-purple-300">View All →</a>
    </div>
    <div class="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-6 gap-4">
      {#each genres as genre}
        <div class="bg-gray-800 p-6 rounded-xl text-center border border-gray-700 hover:border-primary-500 hover:bg-gray-700/50 transition-all duration-300 cursor-pointer">
          <p class="text-white font-medium">{genre}</p>
        </div>
      {/each}
    </div>
  </div>
</section>
