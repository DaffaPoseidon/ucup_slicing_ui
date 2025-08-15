<script lang="ts">
  import Card from '$lib/components/Card.svelte';
  import Button from '$lib/components/Button.svelte';
  
  // Component state
  let selectedGenre = 'All';
  
  const genres = ['All', 'Romance', 'Fantasy', 'Mystery', 'Sci-Fi', 'Horror', 'Drama'];
  
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
      genre: 'Adventure',
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
  
  const newReleases = [
    { title: 'Whispers in the Dark', author: 'Sarah Miller', genre: 'Horror', rating: 4.5 },
    { title: 'The Alchemist\'s Daughter', author: 'Robert Johnson', genre: 'Fantasy', rating: 4.7 },
    { title: 'Midnight Serenade', author: 'Lisa Wang', genre: 'Romance', rating: 4.6 },
    { title: 'Chronicles Blue', author: 'Michael Brown', genre: 'Adventure', rating: 4.4 }
  ];
  
  const editorsPicks = [
    { title: 'The Last Magician', author: 'Alexandra Stone', genre: 'Fantasy', rating: 4.8 },
    { title: 'Crimson Empire', author: 'Victoria Cross', genre: 'Fantasy', rating: 4.9 },
    { title: 'Chronicles of the Forgotten', author: 'Thomas Grey', genre: 'Adventure', rating: 4.7 },
    { title: 'Shadows Convergence', author: 'Amanda White', genre: 'Mystery', rating: 4.6 }
  ];
  
  const latestChapters = [
    { title: 'The Last Magician', chapter: 46, timeAgo: '2 hours ago' },
    { title: 'Shadow of Tomorrow', chapter: 33, timeAgo: '4 hours ago' },
    { title: 'Memories of the Past', chapter: 29, timeAgo: '6 hours ago' },
    { title: 'The Alchemist\'s Legacy', chapter: 41, timeAgo: '8 hours ago' },
    { title: 'City of Dragons', chapter: 52, timeAgo: '12 hours ago' }
  ];
  
  const testimonialsData = [
    { name: "Sarah L.", text: "Novella has completely transformed how I discover new stories. The recommendations are spot on!", avatar: "S", affiliation: "Fantasy Reader" },
    { name: "Michael R.", text: "As an aspiring writer, this platform gave me the confidence to share my work with the world.", avatar: "M", affiliation: "Horror Writer" },
    { name: "Anna K.", text: "I love how engaged the community is. The comments and feedback really help authors grow.", avatar: "A", affiliation: "Romance Enthusiast" }
  ];
</script>

<!-- Statistics Section -->
<section class="py-20 bg-gray-800/50">
  <div class="max-w-full mx-auto px-4 sm:px-6 lg:px-8">
    <div class="grid grid-cols-2 md:grid-cols-4 gap-8">
      <div class="text-center bg-gray-800 p-6 rounded-xl border border-gray-700">
        <div class="text-3xl font-bold text-white mb-2">50K+</div>
        <div class="text-gray-400">Original Stories</div>
      </div>
      <div class="text-center bg-gray-800 p-6 rounded-xl border border-gray-700">
        <div class="text-3xl font-bold text-white mb-2">1.2M+</div>
        <div class="text-gray-400">Active Readers</div>
      </div>
      <div class="text-center bg-gray-800 p-6 rounded-xl border border-gray-700">
        <div class="text-3xl font-bold text-white mb-2">75K+</div>
        <div class="text-gray-400">Published Authors</div>
      </div>
      <div class="text-center bg-gray-800 p-6 rounded-xl border border-gray-700">
        <div class="text-3xl font-bold text-white mb-2">100+</div>
        <div class="text-gray-400">Writing Awards</div>
      </div>
    </div>
  </div>
</section>

<!-- Community Testimonials -->
<section class="py-20">
  <div class="max-w-full mx-auto px-4 sm:px-6 lg:px-8">
    <h2 class="text-3xl font-bold text-center text-white mb-4">What Our Community Says</h2>
    <p class="text-gray-400 text-center mb-12 max-w-2xl mx-auto">
      Discover why millions of readers and writers choose Novella as their favorite platform for original stories.
    </p>
    <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
      {#each testimonialsData as testimonial}
        <div class="bg-gray-800 p-6 rounded-xl border border-gray-700">
          <!-- Header: Profile pic and name/affiliation -->
          <div class="flex items-start mb-5">
            <!-- Profile picture -->
            <div class="w-12 h-12 bg-white rounded-full flex items-center justify-center flex-shrink-0">
              <span class="text-primary-600 font-medium">{testimonial.avatar}</span>
            </div>
            
            <!-- Name and affiliation -->
            <div class="ml-3">
              <p class="text-white font-semibold">{testimonial.name}</p>
              <p class="text-purple-400 text-sm">{testimonial.affiliation}</p>
            </div>
          </div>
          
          <!-- Review text -->
          <p class="text-gray-300 mb-5 italic">"{testimonial.text}"</p>
          
          <!-- Stars at the bottom -->
          <div class="flex">
            {#each Array(5) as _, i}
              <svg class="h-5 w-5 text-yellow-400 fill-current" viewBox="0 0 20 20">
                <path d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z" />
              </svg>
            {/each}
          </div>
        </div>
      {/each}
    </div>
  </div>

  <!-- Special Announcement Card with larger margin -->
  <div class="max-w-full mx-auto px-4 sm:px-6 lg:px-8 mt-24">
    <div class="bg-gray-800 p-6 rounded-xl border border-gray-700 max-w-3xl mx-auto">
      <!-- Row 1: Bell icon, Title, and "New" badge -->
      <div class="flex items-center justify-center mb-4">
        <svg class="h-6 w-6 text-purple-400 mr-3" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 17h5l-1.405-1.405A2.032 2.032 0 0118 14.158V11a6.002 6.002 0 00-4-5.659V5a2 2 0 10-4 0v.341C7.67 6.165 6 8.388 6 11v3.159c0 .538-.214 1.055-.595 1.436L4 17h5m6 0v1a3 3 0 11-6 0v-1m6 0H9" />
        </svg>
        <h3 class="text-xl font-bold text-white">Summer Writing Contest</h3>
        <span class="ml-3 px-2 py-1 text-xs font-bold text-white rounded-full border border-white border-opacity-30">New</span>
      </div>
      
      <!-- Row 2: Description text with justify -->
      <p class="text-gray-300 mb-4 text-justify">
        Summer Writing Contest announced! Join our annual writing competition and showcase your talent. The theme this year is "Unexpected Journeys" and submissions are open until September 15th. Winners will receive prizes and featured placement on our platform.
      </p>
      
      <!-- Row 3: View All link -->
      <div class="text-center">
        <a href="#" class="text-purple-400 hover:text-purple-300 font-medium">View All &gt;</a>
      </div>
    </div>
  </div>
</section>

<!-- Trending & Rankings Section -->
<section class="py-20 bg-gray-800/30">
  <div class="max-w-full mx-auto px-4 sm:px-6 lg:px-8">
    <div class="grid grid-cols-1 lg:grid-cols-3 gap-12">
      <!-- Trending Now -->
      <div class="lg:col-span-2">
        <div class="flex items-center justify-between mb-8">
          <h2 class="text-2xl font-bold text-white">Trending Now</h2>
          <a href="#" class="text-purple-400 hover:text-purple-300">View All →</a>
        </div>
        <div class="grid grid-cols-2 gap-6">
          {#each trendingBooks as book}
            <div class="bg-gray-800 rounded-xl overflow-hidden border border-gray-700 hover:border-primary-500 transition-colors">
              <div class="relative">
                <div class="bg-gray-700 h-48 flex items-center justify-center">
                  <svg class="h-12 w-12 text-gray-500" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 6.253v13m0-13C10.832 5.477 9.246 5 7.5 5S4.168 5.477 3 6.253v13C4.168 18.477 5.754 18 7.5 18s3.332.477 4.5 1.253m0-13C13.168 5.477 14.754 5 16.5 5c1.746 0 3.332.477 4.5 1.253v13C19.832 18.477 18.246 18 16.5 18c-1.746 0-3.332.477-4.5 1.253" />
                  </svg>
                </div>
                <span class={`absolute top-3 left-3 px-2 py-1 text-xs rounded-full ${
                  book.status === 'Hot' ? 'bg-red-500 text-white' : 'bg-green-500 text-white'
                }`}>
                  {book.status}
                </span>
              </div>
              <div class="p-4">
                <h3 class="text-white font-semibold mb-1">{book.title}</h3>
                <p class="text-gray-400 text-sm mb-1">by {book.author}</p>
                <p class="text-gray-500 text-xs mb-2">{book.genre}</p>
                <p class="text-gray-400 text-xs mb-3 line-clamp-2">{book.description}</p>
                <div class="flex items-center justify-between">
                  <div class="flex items-center space-x-2">
                    <div class="flex">
                      {#each Array(5) as _, i}
                        <svg class="h-4 w-4 text-yellow-400 fill-current" viewBox="0 0 20 20">
                          <path d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z" />
                        </svg>
                      {/each}
                    </div>
                    <span class="text-gray-400 text-xs">{book.rating}</span>
                  </div>
                  <span class="text-primary-400 text-sm">Read →</span>
                </div>
                <div class="mt-2 text-gray-500 text-xs">
                  {book.chapters} chapters
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
          <a href="#" class="text-primary-400 hover:text-primary-300">Full Rankings →</a>
        </div>
        <div class="bg-gray-800 rounded-xl border border-gray-700">
          <!-- Genre Selector -->
          <div class="p-4 border-b border-gray-700">
            <select bind:value={selectedGenre} class="bg-gray-700 text-white px-3 py-2 rounded-lg border border-gray-600 focus:border-primary-500 focus:outline-none w-full">
              {#each genres as genre}
                <option value={genre}>{genre}</option>
              {/each}
            </select>
          </div>
          <!-- Rankings List -->
          <div class="p-4">
            <div class="space-y-4">
              {#each weeklyRankings as item}
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
                    <p class="text-gray-500 text-xs">{item.genre}</p>
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

<!-- New Releases -->
<section class="py-20">
  <div class="max-w-full mx-auto px-4 sm:px-6 lg:px-8">
    <div class="flex items-center justify-between mb-8">
      <h2 class="text-2xl font-bold text-white">New Releases</h2>
      <a href="#" class="text-purple-400 hover:text-purple-300">View All →</a>
    </div>
    <div class="grid grid-cols-2 md:grid-cols-4 gap-6">
      {#each newReleases as book}
        <div class="bg-gray-800 rounded-xl overflow-hidden border border-gray-700 hover:border-primary-500 transition-colors">
          <div class="bg-gray-700 h-48 flex items-center justify-center">
            <svg class="h-12 w-12 text-gray-500" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 6.253v13m0-13C10.832 5.477 9.246 5 7.5 5S4.168 5.477 3 6.253v13C4.168 18.477 5.754 18 7.5 18s3.332.477 4.5 1.253m0-13C13.168 5.477 14.754 5 16.5 5c1.746 0 3.332.477 4.5 1.253v13C19.832 18.477 18.246 18 16.5 18c-1.746 0-3.332.477-4.5 1.253" />
            </svg>
          </div>
          <div class="p-4">
            <h3 class="text-white font-semibold mb-1">{book.title}</h3>
            <p class="text-gray-400 text-sm mb-1">by {book.author}</p>
            <p class="text-gray-500 text-xs mb-2">{book.genre}</p>
            <div class="flex items-center justify-between">
              <div class="flex items-center">
                <div class="flex">
                  {#each Array(5) as _, i}
                    <svg class="h-4 w-4 text-yellow-400 fill-current" viewBox="0 0 20 20">
                      <path d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z" />
                    </svg>
                  {/each}
                </div>
                <span class="text-gray-400 text-xs ml-1">{book.rating}</span>
              </div>
              <span class="text-primary-400 text-sm">Read →</span>
            </div>
          </div>
        </div>
      {/each}
    </div>
  </div>
</section>

<!-- Browse by Genre -->
<section class="py-20 bg-gray-800/30">
  <div class="max-w-full mx-auto px-4 sm:px-6 lg:px-8">
    <div class="flex items-center justify-between mb-8">
      <h2 class="text-2xl font-bold text-white">Browse by Genre</h2>
      <a href="#" class="text-purple-400 hover:text-purple-300">View All →</a>
    </div>
    <div class="grid grid-cols-3 md:grid-cols-6 gap-4">
      {#each ["Romance", "Fantasy", "Mystery", "Sci-Fi", "Horror", "Drama"] as genre}
        <div class="bg-gray-800 p-6 rounded-xl text-center border border-gray-700 hover:border-primary-500 transition-colors cursor-pointer">
          <p class="text-white font-medium">{genre}</p>
        </div>
      {/each}
    </div>
  </div>
</section>

<!-- Editor's Picks -->
<section class="py-20">
  <div class="max-w-full mx-auto px-4 sm:px-6 lg:px-8">
    <div class="flex items-center justify-between mb-8">
      <h2 class="text-2xl font-bold text-white">Editor's Picks</h2>
      <a href="#" class="text-purple-400 hover:text-purple-300">View All →</a>
    </div>
    <div class="grid grid-cols-2 md:grid-cols-4 gap-6">
      {#each editorsPicks as book}
        <div class="bg-gray-800 rounded-xl overflow-hidden border border-gray-700 hover:border-primary-500 transition-colors">
          <div class="relative">
            <div class="bg-gray-700 h-48 flex items-center justify-center">
              <svg class="h-12 w-12 text-gray-500" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4M7.835 4.697a3.42 3.42 0 001.946-.806 3.42 3.42 0 014.438 0 3.42 3.42 0 001.946.806 3.42 3.42 0 013.138 3.138 3.42 3.42 0 00.806 1.946 3.42 3.42 0 010 4.438 3.42 3.42 0 00-.806 1.946 3.42 3.42 0 01-3.138 3.138 3.42 3.42 0 00-1.946.806 3.42 3.42 0 01-4.438 0 3.42 3.42 0 00-1.946-.806 3.42 3.42 0 01-3.138-3.138 3.42 3.42 0 00-.806-1.946 3.42 3.42 0 010-4.438 3.42 3.42 0 00.806-1.946 3.42 3.42 0 013.138-3.138z" />
              </svg>
            </div>
            <span class="absolute top-3 left-3 bg-yellow-500 text-black px-2 py-1 text-xs rounded-full font-bold">
              Editor's Pick
            </span>
          </div>
          <div class="p-4">
            <h3 class="text-white font-semibold mb-1">{book.title}</h3>
            <p class="text-gray-400 text-sm mb-1">by {book.author}</p>
            <p class="text-gray-500 text-xs mb-2">{book.genre}</p>
            <div class="flex items-center justify-between">
              <div class="flex items-center">
                <div class="flex">
                  {#each Array(5) as _, i}
                    <svg class="h-4 w-4 text-yellow-400 fill-current" viewBox="0 0 20 20">
                      <path d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z" />
                    </svg>
                  {/each}
                </div>
                <span class="text-gray-400 text-xs ml-1">{book.rating}</span>
              </div>
              <span class="text-primary-400 text-sm">Read →</span>
            </div>
          </div>
        </div>
      {/each}
    </div>
  </div>
</section>

<!-- Tools Section -->
<section class="py-20 bg-gray-800/30">
  <div class="max-w-full mx-auto px-4 sm:px-6 lg:px-8">
    <h2 class="text-2xl font-bold text-white text-center mb-12">Powerful Tools for Writers & Readers</h2>
    <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
      <div class="bg-gray-800 p-8 rounded-xl border border-gray-700">
        <svg class="h-12 w-12 text-primary-400 mb-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15.232 5.232l3.536 3.536m-2.036-5.036a2.5 2.5 0 113.536 3.536L6.5 21.036H3v-3.572L16.732 3.732z" />
        </svg>
        <h3 class="text-xl font-bold text-white mb-4">Creative & Analytics</h3>
        <p class="text-gray-300 mb-6">
          Get real-time reader insights with our advanced analytics dashboard. Track your story's performance, reader engagement, and optimize your content.
        </p>
        <button class="bg-primary-600 hover:bg-primary-700 text-white px-6 py-3 rounded-lg transition-colors">
          Get Started →
        </button>
      </div>
      <div class="bg-gray-800 p-8 rounded-xl border border-gray-700">
        <svg class="h-12 w-12 text-primary-400 mb-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 6.253v13m0-13C10.832 5.477 9.246 5 7.5 5S4.168 5.477 3 6.253v13C4.168 18.477 5.754 18 7.5 18s3.332.477 4.5 1.253m0-13C13.168 5.477 14.754 5 16.5 5c1.746 0 3.332.477 4.5 1.253v13C19.832 18.477 18.246 18 16.5 18c-1.746 0-3.332.477-4.5 1.253" />
        </svg>
        <h3 class="text-xl font-bold text-white mb-4">Translate Your Stories</h3>
        <p class="text-gray-300 mb-6">
          Reach a global audience with our AI-powered translation tools. Translate your stories into multiple languages while preserving their essence.
        </p>
        <button class="bg-primary-600 hover:bg-primary-700 text-white px-6 py-3 rounded-lg transition-colors">
          Learn More →
        </button>
      </div>
    </div>
  </div>
</section>

<!-- Latest Chapter Updates -->
<section class="py-20">
  <div class="max-w-full mx-auto px-4 sm:px-6 lg:px-8">
    <div class="flex items-center justify-between mb-8">
      <h2 class="text-2xl font-bold text-white">Latest Chapter Updates</h2>
      <a href="#" class="text-purple-400 hover:text-purple-300">View All →</a>
    </div>
    <div class="grid grid-cols-1 md:grid-cols-5 gap-6">
      {#each latestChapters as chapter}
        <div class="bg-gray-800 rounded-xl overflow-hidden border border-gray-700 hover:border-primary-500 transition-colors">
          <div class="bg-gray-700 h-32 flex items-center justify-center">
            <svg class="h-8 w-8 text-gray-500" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 6.253v13m0-13C10.832 5.477 9.246 5 7.5 5S4.168 5.477 3 6.253v13C4.168 18.477 5.754 18 7.5 18s3.332.477 4.5 1.253m0-13C13.168 5.477 14.754 5 16.5 5c1.746 0 3.332.477 4.5 1.253v13C19.832 18.477 18.246 18 16.5 18c-1.746 0-3.332.477-4.5 1.253" />
            </svg>
          </div>
          <div class="p-3">
            <h3 class="text-white font-semibold text-sm mb-1">{chapter.title}</h3>
            <p class="text-gray-400 text-xs mb-2">Chapter {chapter.chapter}</p>
            <p class="text-primary-400 text-xs">{chapter.timeAgo}</p>
          </div>
        </div>
      {/each}
    </div>
  </div>
</section>

<!-- CTA Section -->
<section class="py-20 bg-purple-700">
  <div class="max-w-4xl mx-auto text-center px-4 sm:px-6 lg:px-8">
    <h2 class="text-4xl font-bold text-white mb-6">Have a Story to Tell?</h2>
    <p class="text-purple-100 text-lg mb-8">
      Join thousands of writers and share your stories with our growing community of passionate readers.
    </p>
    <div class="flex flex-col sm:flex-row gap-4 justify-center">
      <button class="border border-white text-white px-8 py-3 rounded-lg font-semibold hover:bg-white hover:text-purple-600 transition-colors">
        Start Writing
      </button>
      <button class="border border-white text-white px-8 py-3 rounded-lg font-semibold hover:bg-white hover:text-purple-600 transition-colors">
        Learn More →
      </button>
    </div>
  </div>
</section>
