<script lang="ts">
  import { PenTool, BookOpen, ChartBar, Globe } from 'lucide-svelte';
  
  // Tools data
  const writerTools = [
    {
      icon: "PenTool",
      title: "Creative & Analytics",
      description: "Get real-time reader insights with our advanced analytics dashboard. Track your story's performance, reader engagement, and optimize your content.",
      buttonText: "Get Started"
    },
    {
      icon: "Globe",
      title: "Translate Your Stories",
      description: "Reach a global audience with our AI-powered translation tools. Translate your stories into multiple languages while preserving their essence.",
      buttonText: "Learn More"
    }
  ];
</script>

<!-- Tools Section -->
<section class="py-20 bg-gray-800/30">
  <div class="max-w-full mx-auto px-4 sm:px-6 lg:px-8">
    <h2 class="text-2xl font-bold text-white text-center mb-12">Powerful Tools for Writers & Readers</h2>
    <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
      <div class="bg-gray-800 p-8 rounded-xl border border-gray-700 hover:border-primary-500 transition-all duration-300 hover:translate-y-[-5px]">
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
      <div class="bg-gray-800 p-8 rounded-xl border border-gray-700 hover:border-primary-500 transition-all duration-300 hover:translate-y-[-5px]">
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
