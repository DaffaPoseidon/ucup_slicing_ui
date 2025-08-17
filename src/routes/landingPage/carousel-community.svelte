<script lang="ts">
  const testimonialsData = [
    { name: "Sarah L.", text: "Novella has completely transformed how I discover new stories. The recommendations are spot on!", avatar: "S", affiliation: "Fantasy Reader" },
    { name: "Michael R.", text: "As an aspiring writer, this platform gave me the confidence to share my work with the world.", avatar: "M", affiliation: "Horror Writer" },
    { name: "Anna K.", text: "I love how engaged the community is. The comments and feedback really help authors grow.", avatar: "A", affiliation: "Romance Enthusiast" }
  ];
</script>

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
              <p class="text-[#9260FE] text-sm">{testimonial.affiliation}</p>
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
  <div class="flex flex-col items-center justify-center gap-[1em] bg-gray-800 p-6 rounded-xl border border-gray-700 mr-[2.5vw] ml-[2.5vw] mt-[10vh] min-[960px]:flex-row min-[960px]:items-center min-[960px]:justify-between">
    <!-- Row 1: Bell icon, Title, and "New" badge -->
    <div class="flex items-center justify-center mb-4 min-[960px]:mb-0">
      <svg class="h-6 w-6 text-[#9260FE] mr-3" fill="none" stroke="currentColor" viewBox="0 0 24 24">
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 17h5l-1.405-1.405A2.032 2.032 0 0118 14.158V11a6.002 6.002 0 00-4-5.659V5a2 2 0 10-4 0v.341C7.67 6.165 6 8.388 6 11v3.159c0 .538-.214 1.055-.595 1.436L4 17h5m6 0v1a3 3 0 11-6 0v-1m6 0H9" />
      </svg>
      <h3 class="text-xl font-bold text-white">Summer Writing Contest</h3>
      <span class="ml-3 px-2 py-1 text-xs font-bold text-white rounded-full border border-white border-opacity-30">New</span>
    </div>
    
    <!-- Row 2: Description text with justify -->
    <p class="text-gray-300 mb-4 min-[960px]:mb-0 text-justify min-[960px]:max-w-md">
      Summer Writing Contest announced! Join for a chance to win $5,000 in prize!
    </p>
    
    <!-- Row 3: View All link -->
    <div class="text-center min-[960px]:text-right">
      <a href="/" class="text-[#9260FE] hover:text-purple-300 font-medium">View All &gt;</a>
    </div>
  </div>
</section>
