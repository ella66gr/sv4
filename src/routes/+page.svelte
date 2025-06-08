<!-- src/routes/+page.svelte -->

<script>
  import { Button, Card, Badge, Input, Label, Textarea, DarkMode } from 'flowbite-svelte';

  let formData = {
    name: '',
    email: '',
    message: ''
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
    <p class="text-xl text-gray-600 dark:text-gray-300 mb-6">
      A modern web development stack with production-ready components
    </p>

    <!-- Theme Toggle -->
    <div class="flex justify-center mb-6">
      <DarkMode class="gap-2 bg-gray-100 hover:bg-gray-200 text-gray-900 dark:bg-gray-700 dark:hover:bg-gray-600 dark:text-white border border-gray-300 dark:border-gray-600 px-4 py-2 rounded-lg" />
    </div>

    <!-- Technology Badges -->
    <div class="flex gap-2 justify-center flex-wrap">
      <Badge color="blue">SvelteKit</Badge>
      <Badge color="purple">Tailwind CSS v4</Badge>
      <Badge color="green">Flowbite Svelte</Badge>
      <Badge color="orange">Vite</Badge>
    </div>
  </div>

  <!-- Feature Grid with properly styled Cards -->
  <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6 mb-12">
    <Card class="p-6 bg-white dark:bg-gray-800 border border-gray-200 dark:border-gray-700 rounded-lg shadow-sm hover:shadow-md transition-shadow">
      <h3 class="text-xl font-semibold text-gray-900 dark:text-white mb-3">⚡ Fast Development</h3>
      <p class="text-gray-600 dark:text-gray-300 mb-4">
        Hot module replacement and instant feedback with Vite's lightning-fast development server.
      </p>
      <Badge color="blue">Performance</Badge>
    </Card>

    <Card class="p-6 bg-white dark:bg-gray-800 border border-gray-200 dark:border-gray-700 rounded-lg shadow-sm hover:shadow-md transition-shadow">
      <h3 class="text-xl font-semibold text-gray-900 dark:text-white mb-3">🎨 Modern Styling</h3>
      <p class="text-gray-600 dark:text-gray-300 mb-4">
        Tailwind CSS v4 with improved performance, better developer experience, and new features.
      </p>
      <Badge color="purple">Design</Badge>
    </Card>

    <Card class="p-6 bg-white dark:bg-gray-800 border border-gray-200 dark:border-gray-700 rounded-lg shadow-sm hover:shadow-md transition-shadow">
      <h3 class="text-xl font-semibold text-gray-900 dark:text-white mb-3">🧩 Rich Components</h3>
      <p class="text-gray-600 dark:text-gray-300 mb-4">
        Flowbite Svelte provides 45+ components with excellent theming and accessibility.
      </p>
      <Badge color="green">Components</Badge>
    </Card>
  </div>

  <!-- Interactive Demo with proper Card styling -->
  <Card class="max-w-2xl mx-auto mb-12 p-6 bg-white dark:bg-gray-800 border border-gray-200 dark:border-gray-700 rounded-lg shadow-sm">
    <h2 class="text-2xl font-bold text-gray-900 dark:text-white mb-2">Contact Form Demo</h2>
    <p class="text-gray-600 dark:text-gray-300 mb-6">
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
          bind:value={formData.message}
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
  </Card>

  <!-- Technology Stack Info -->
  <div class="mt-16 text-center">
    <h2 class="text-2xl font-bold text-gray-900 dark:text-white mb-8">Why This Stack?</h2>

    <div class="grid grid-cols-1 md:grid-cols-2 gap-8 max-w-4xl mx-auto">
      <div class="text-left">
        <h3 class="text-lg font-semibold text-gray-900 dark:text-white mb-3">Developer Experience</h3>
        <ul class="space-y-2 text-gray-600 dark:text-gray-300">
          <li>• TypeScript support out of the box</li>
          <li>• Hot reload for instant feedback</li>
          <li>• Modern build tooling with Vite</li>
          <li>• Excellent debugging capabilities</li>
        </ul>
      </div>

      <div class="text-left">
        <h3 class="text-lg font-semibold text-gray-900 dark:text-white mb-3">Production Ready</h3>
        <ul class="space-y-2 text-gray-600 dark:text-gray-300">
          <li>• Optimized builds and code splitting</li>
          <li>• SEO-friendly with SSR support</li>
          <li>• Accessible components by default</li>
          <li>• Easy deployment to any platform</li>
        </ul>
      </div>
    </div>
  </div>
</div>