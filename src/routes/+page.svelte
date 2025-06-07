<script>
  import { Button, Card, Badge, Input, Label, Textarea } from 'flowbite-svelte';
  import { toggleDarkMode } from '$lib/utils';
  import { onMount } from 'svelte';

  onMount(() => {
    // Initialize dark mode
    if (typeof document !== 'undefined') {
      const savedMode = localStorage.getItem('darkMode');
      if (savedMode === 'true') {
        document.documentElement.classList.add('dark');
      }
    }
  });

  let formData = {
    name: '',
    email: ''
  };
</script>

<svelte:head>
  <title>SvelteKit + Tailwind CSS v4 + Flowbite Svelte</title>
  <meta name="description" content="Modern SvelteKit setup with Tailwind CSS v4 and Flowbite Svelte components" />
</svelte:head>

<div class="container mx-auto px-4 py-8">
  <!-- Header -->
  <div class="text-center mb-12">
    <h1 class="text-4xl font-bold tracking-tight mb-4 text-gray-900 dark:text-white">
      SvelteKit + Tailwind CSS v4 + Flowbite Svelte
    </h1>
    <p class="text-xl text-gray-600 dark:text-gray-400 mb-6">
      A modern web development stack with production-ready components
    </p>

    <!-- Theme Toggle -->
    <div class="flex justify-center mb-6">
      <Button on:click={toggleDarkMode} color="alternative" class="gap-2">
        <span class="dark:hidden">🌙 Dark Mode</span>
        <span class="hidden dark:inline">☀️ Light Mode</span>
      </Button>
    </div>

    <!-- Technology Badges -->
    <div class="flex gap-2 justify-center flex-wrap">
      <Badge color="blue">SvelteKit</Badge>
      <Badge color="purple">Tailwind CSS v4</Badge>
      <Badge color="green">Flowbite Svelte</Badge>
      <Badge color="orange">Vite</Badge>
    </div>
  </div>

  <!-- Feature Grid -->
  <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6 mb-12">
    <Card class="max-w-none">
      <h3 class="text-xl font-semibold text-gray-900 dark:text-white mb-3">⚡ Fast Development</h3>
      <p class="text-gray-600 dark:text-gray-400 mb-4">
        Hot module replacement and instant feedback with Vite's lightning-fast development server.
      </p>
      <Badge color="blue">Performance</Badge>
    </Card>

    <Card class="max-w-none">
      <h3 class="text-xl font-semibold text-gray-900 dark:text-white mb-3">🎨 Modern Styling</h3>
      <p class="text-gray-600 dark:text-gray-400 mb-4">
        Tailwind CSS v4 with improved performance, better developer experience, and new features.
      </p>
      <Badge color="purple">Design</Badge>
    </Card>

    <Card class="max-w-none">
      <h3 class="text-xl font-semibold text-gray-900 dark:text-white mb-3">🧩 Rich Components</h3>
      <p class="text-gray-600 dark:text-gray-400 mb-4">
        Flowbite Svelte provides 45+ components with excellent theming and accessibility.
      </p>
      <Badge color="green">Components</Badge>
    </Card>
  </div>

  <!-- Interactive Demo -->
  <Card class="max-w-2xl mx-auto">
    <div class="p-6">
      <h2 class="text-2xl font-bold text-gray-900 dark:text-white mb-2">Contact Form Demo</h2>
      <p class="text-gray-600 dark:text-gray-400 mb-6">
        Demonstrating Flowbite Svelte form components with proper theming
      </p>

      <form class="space-y-4">
        <div>
          <Label for="name" class="mb-2">Full Name</Label>
          <Input 
            id="name" 
            bind:value={formData.name}
            placeholder="Enter your full name"
            required
          />
        </div>

        <div>
          <Label for="email" class="mb-2">Email Address</Label>
          <Input 
            id="email" 
            type="email"
            bind:value={formData.email}
            placeholder="your.email@example.com"
            required
          />
        </div>

        <div>
          <Label for="message" class="mb-2">Message</Label>
          <Textarea 
            id="message" 
            placeholder="Tell us about your project..."
            rows="4"
          />
        </div>

        <div class="flex gap-3 pt-4">
          <Button type="submit" class="flex-1">
            Send Message
          </Button>
          <Button color="alternative" type="button">
            Save Draft
          </Button>
        </div>
      </form>
    </div>
  </Card>

  <!-- Technology Stack Info -->
  <div class="mt-16 text-center">
    <h2 class="text-2xl font-bold text-gray-900 dark:text-white mb-8">Why This Stack?</h2>

    <div class="grid grid-cols-1 md:grid-cols-2 gap-8 max-w-4xl mx-auto">
      <div class="text-left">
        <h3 class="text-lg font-semibold text-gray-900 dark:text-white mb-3">Developer Experience</h3>
        <ul class="space-y-2 text-gray-600 dark:text-gray-400">
          <li>• TypeScript support out of the box</li>
          <li>• Hot reload for instant feedback</li>
          <li>• Modern build tooling with Vite</li>
          <li>• Excellent debugging capabilities</li>
        </ul>
      </div>

      <div class="text-left">
        <h3 class="text-lg font-semibold text-gray-900 dark:text-white mb-3">Production Ready</h3>
        <ul class="space-y-2 text-gray-600 dark:text-gray-400">
          <li>• Optimized builds and code splitting</li>
          <li>• SEO-friendly with SSR support</li>
          <li>• Accessible components by default</li>
          <li>• Easy deployment to any platform</li>
        </ul>
      </div>
    </div>
  </div>
</div>