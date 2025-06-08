<!-- src/routes/themes/+page.svelte -->

<script>
  // Import Flowbite Svelte components
  import { 
    Button, 
    Card, 
    Badge, 
    Input, 
    Label,
    Alert,
    DarkMode,
    Breadcrumb,
    BreadcrumbItem
  } from 'flowbite-svelte';

  // Current selected theme state
  let currentTheme = 'blue';

  // Available theme options with display properties
  const themes = [
    { name: 'Blue', value: 'blue', class: 'bg-blue-600', description: 'Professional & trustworthy' },
    { name: 'Green', value: 'green', class: 'bg-green-600', description: 'Success & growth' },
    { name: 'Red', value: 'red', class: 'bg-red-600', description: 'Energy & urgency' },
    { name: 'Purple', value: 'purple', class: 'bg-purple-600', description: 'Creative & premium' },
    { name: 'Yellow', value: 'yellow', class: 'bg-yellow-500', description: 'Attention & optimism' },
    { name: 'Pink', value: 'pink', class: 'bg-pink-600', description: 'Modern & playful' },
  ];

  // Function to apply a selected theme
  function applyTheme(theme) {
    currentTheme = theme;
  }
</script>

<!-- Page head metadata -->
<svelte:head>
  <title>Themes Demo - Flowbite Svelte</title>
</svelte:head>

<!-- Main container with proper responsive padding -->
<div class="min-h-screen bg-gray-50 dark:bg-gray-900">
  
  <!-- Header Section - Full width with proper spacing -->
  <div class="bg-white dark:bg-gray-800 border-b border-gray-200 dark:border-gray-700">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-12">
      <!-- Breadcrumb -->
      <div class="mb-6">
        <Breadcrumb>
          <BreadcrumbItem href="/" home>Home</BreadcrumbItem>
          <BreadcrumbItem>Themes</BreadcrumbItem>
        </Breadcrumb>
      </div>

      <div class="text-center">
        <h1 class="text-4xl lg:text-5xl font-bold tracking-tight text-gray-900 dark:text-white mb-4">
          Flowbite Svelte Themes Demo
        </h1>
        <p class="text-xl text-gray-600 dark:text-gray-300 mb-8 max-w-3xl mx-auto">
          Explore comprehensive theming capabilities with semantic color palettes, dark mode support, and professional design systems
        </p>

        <!-- Theme Toggle -->
        <div class="flex justify-center mb-8">
          <DarkMode class="gap-2 bg-gray-100 hover:bg-gray-200 text-gray-900 dark:bg-gray-700 dark:hover:bg-gray-600 dark:text-white border border-gray-300 dark:border-gray-600 px-4 py-2 rounded-lg" />
        </div>

        <!-- Feature Badges -->
        <div class="flex gap-3 justify-center flex-wrap">
          <Badge color="blue" class="text-sm px-3 py-1.5">Dynamic Theming</Badge>
          <Badge color="purple" class="text-sm px-3 py-1.5">Dark Mode</Badge>
          <Badge color="green" class="text-sm px-3 py-1.5">Accessibility Ready</Badge>
          <Badge color="orange" class="text-sm px-3 py-1.5">Semantic Colors</Badge>
        </div>
      </div>
    </div>
  </div>

  <!-- Main Content Area -->
  <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-12">

    <!-- Theme Explanation Card -->
    <div class="mb-16">
      <Card class="p-8 bg-gradient-to-br from-indigo-50 to-purple-100 dark:from-indigo-900/20 dark:to-purple-900/20 border border-indigo-200 dark:border-indigo-800 rounded-lg shadow-sm">
        <div class="flex items-start mb-6">
          <div class="w-12 h-12 bg-indigo-100 dark:bg-indigo-900 rounded-lg flex items-center justify-center mr-4 flex-shrink-0">
            <span class="text-2xl">🎨</span>
          </div>
          <div>
            <h2 class="text-2xl font-bold text-gray-900 dark:text-white mb-2">Interactive Theme System</h2>
            <p class="text-gray-600 dark:text-gray-300">Experience how Flowbite Svelte components adapt to different color themes while maintaining accessibility and visual hierarchy</p>
          </div>
        </div>

        <div class="grid grid-cols-1 lg:grid-cols-2 gap-8">
          <div>
            <h3 class="text-lg font-semibold text-gray-900 dark:text-white mb-4">Theme Features</h3>
            <ul class="space-y-2 text-gray-600 dark:text-gray-300">
              <li class="flex items-start">
                <span class="text-green-500 mr-3 mt-1">✓</span>
                <span><strong>Live preview:</strong> See theme changes applied instantly across all components</span>
              </li>
              <li class="flex items-start">
                <span class="text-green-500 mr-3 mt-1">✓</span>
                <span><strong>Semantic colors:</strong> Each theme conveys meaning and emotional association</span>
              </li>
              <li class="flex items-start">
                <span class="text-green-500 mr-3 mt-1">✓</span>
                <span><strong>Accessibility maintained:</strong> Proper contrast ratios in all themes and modes</span>
              </li>
            </ul>
          </div>

          <div>
            <h3 class="text-lg font-semibold text-gray-900 dark:text-white mb-4">How to Use</h3>
            <ul class="space-y-2 text-gray-600 dark:text-gray-300">
              <li class="flex items-start">
                <span class="text-blue-500 mr-3 mt-1">1.</span>
                <span>Click any theme color below to apply it</span>
              </li>
              <li class="flex items-start">
                <span class="text-blue-500 mr-3 mt-1">2.</span>
                <span>Watch components update with the new color scheme</span>
              </li>
              <li class="flex items-start">
                <span class="text-blue-500 mr-3 mt-1">3.</span>
                <span>Toggle dark mode to see theme behavior in both modes</span>
              </li>
            </ul>
          </div>
        </div>
      </Card>
    </div>

    <!-- Theme Selection Section -->
    <div class="mb-16">
      <Card class="p-8 bg-white dark:bg-gray-800 border border-gray-200 dark:border-gray-700 rounded-lg shadow-sm">
        <div class="mb-8">
          <h2 class="text-2xl font-bold text-gray-900 dark:text-white mb-2">Available Color Themes</h2>
          <p class="text-gray-600 dark:text-gray-400">Choose from our carefully curated palette of semantic color themes</p>
        </div>

        <!-- Theme selector grid -->
        <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6">
          {#each themes as theme}
            <button
              class="flex flex-col items-center p-6 border-2 rounded-lg transition-all duration-200 hover:shadow-lg hover:scale-105 {currentTheme === theme.value ? 'border-' + theme.value + '-600 bg-' + theme.value + '-50 dark:bg-' + theme.value + '-900/20' : 'border-gray-200 dark:border-gray-700 hover:border-gray-300 dark:hover:border-gray-600'}"
              on:click={() => applyTheme(theme.value)}
            >
              <!-- Theme color circle -->
              <div class="w-16 h-16 {theme.class} rounded-full mb-4 shadow-lg"></div>
              <!-- Theme name -->
              <span class="text-lg font-semibold text-gray-900 dark:text-white mb-2">{theme.name}</span>
              <!-- Theme description -->
              <span class="text-sm text-gray-600 dark:text-gray-400 text-center">{theme.description}</span>
              
              {#if currentTheme === theme.value}
                <div class="mt-3">
                  <Badge color={theme.value} class="text-xs">Active Theme</Badge>
                </div>
              {/if}
            </button>
          {/each}
        </div>
      </Card>
    </div>

    <!-- Live Demo Section - Balanced paired layout -->
    <div class="grid grid-cols-1 xl:grid-cols-2 gap-8 mb-16">
      
      <!-- Interactive Components Card -->
      <Card class="p-8 bg-white dark:bg-gray-800 border border-gray-200 dark:border-gray-700 rounded-lg shadow-sm">
        <div class="mb-6">
          <div class="flex items-center mb-4">
            <div class="w-10 h-10 bg-blue-100 dark:bg-blue-900 rounded-lg flex items-center justify-center mr-3">
              <span class="text-lg">🎛️</span>
            </div>
            <h3 class="text-xl font-semibold text-gray-900 dark:text-white">Interactive Elements</h3>
          </div>
          <p class="text-gray-600 dark:text-gray-400">Components using the current <Badge color={currentTheme} class="mx-1">{currentTheme}</Badge> theme with hover effects</p>
        </div>

        <div class="space-y-6">
          <!-- Themed Buttons Section -->
          <div>
            <Label class="text-sm font-medium text-gray-900 dark:text-white mb-3 block">
              Themed Buttons
            </Label>
            <div class="flex flex-wrap gap-3">
              <Button color={currentTheme}>Primary</Button>
              <Button color={currentTheme} outline>Outline</Button>
              <Button color="alternative">Alternative</Button>
              <Button color="dark">Dark</Button>
            </div>
          </div>

          <!-- Themed Badges Section -->
          <div>
            <Label class="text-sm font-medium text-gray-900 dark:text-white mb-3 block">
              Themed Badges
            </Label>
            <div class="flex flex-wrap gap-2">
              <Badge color={currentTheme}>Active</Badge>
              <Badge color={currentTheme} large>Featured</Badge>
              <Badge color="alternative">Default</Badge>
              <Badge color="green">Success</Badge>
              <Badge color="red">Error</Badge>
            </div>
          </div>

          <!-- Form Elements Section -->
          <div>
            <Label class="text-sm font-medium text-gray-900 dark:text-white mb-3 block">
              Form Elements
            </Label>
            <div class="space-y-3">
              <Input placeholder="Input with themed focus state" class="w-full" />
              <div class="flex gap-2">
                <Button color={currentTheme} size="sm">Submit</Button>
                <Button color="alternative" size="sm">Cancel</Button>
              </div>
            </div>
          </div>
        </div>
      </Card>

      <!-- Status System Card -->
      <Card class="p-8 bg-white dark:bg-gray-800 border border-gray-200 dark:border-gray-700 rounded-lg shadow-sm">
        <div class="mb-6">
          <div class="flex items-center mb-4">
            <div class="w-10 h-10 bg-yellow-100 dark:bg-yellow-900 rounded-lg flex items-center justify-center mr-3">
              <span class="text-lg">📊</span>
            </div>
            <h3 class="text-xl font-semibold text-gray-900 dark:text-white">Status System</h3>
          </div>
          <p class="text-gray-600 dark:text-gray-400">Semantic colors for consistent user feedback across all themes</p>
        </div>

        <!-- Alert components demonstrating proper dark mode text colors -->
        <div class="space-y-4">
          <!-- Information Alert -->
          <Alert color="blue">
            <svg slot="icon" class="w-4 h-4" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="currentColor" viewBox="0 0 20 20">
              <path d="M10 .5a9.5 9.5 0 1 0 9.5 9.5A9.51 9.51 0 0 0 10 .5ZM9.5 4a1.5 1.5 0 1 1 0 3 1.5 1.5 0 0 1 0-3ZM12 15H8a1 1 0 0 1 0-2h1v-3H8a1 1 0 0 1 0-2h2a1 1 0 0 1 1 1v4h1a1 1 0 0 1 0 2Z"/>
            </svg>
            <span class="font-medium">Information:</span> Here's some helpful information for you.
          </Alert>

          <!-- Success Alert -->
          <Alert color="green">
            <svg slot="icon" class="w-4 h-4" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="currentColor" viewBox="0 0 20 20">
              <path d="M10 .5a9.5 9.5 0 1 0 9.5 9.5A9.51 9.51 0 0 0 10 .5Zm3.707 8.207-4 4a1 1 0 0 1-1.414 0l-2-2a1 1 0 0 1 1.414-1.414L9 10.586l3.293-3.293a1 1 0 0 1 1.414 1.414Z"/>
            </svg>
            <span class="font-medium">Success:</span> Your theme has been applied successfully.
          </Alert>

          <!-- Warning Alert -->
          <Alert color="yellow">
            <svg slot="icon" class="w-4 h-4" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="currentColor" viewBox="0 0 20 20">
              <path d="M10 .5a9.5 9.5 0 1 0 9.5 9.5A9.51 9.51 0 0 0 10 .5ZM10 15a1 1 0 1 1 0-2 1 1 0 0 1 0 2Zm1-4a1 1 0 0 1-2 0V6a1 1 0 0 1 2 0v5Z"/>
            </svg>
            <span class="font-medium">Warning:</span> Consider contrast when choosing themes.
          </Alert>

          <!-- Error Alert -->
          <Alert color="red">
            <svg slot="icon" class="w-4 h-4" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="currentColor" viewBox="0 0 20 20">
              <path d="M10 .5a9.5 9.5 0 1 0 9.5 9.5A9.51 9.51 0 0 0 10 .5ZM10 15a1 1 0 1 1 0-2 1 1 0 0 1 0 2Zm1-4a1 1 0 0 1-2 0V6a1 1 0 0 1 2 0v5Z"/>
            </svg>
            <span class="font-medium">Error:</span> Theme application failed. Please try again.
          </Alert>
        </div>
      </Card>
    </div>

    <!-- Typography & Dark Mode Section -->
    <div class="grid grid-cols-1 xl:grid-cols-2 gap-8 mb-16">
      
      <!-- Typography Showcase -->
      <Card class="p-8 bg-white dark:bg-gray-800 border border-gray-200 dark:border-gray-700 rounded-lg shadow-sm">
        <div class="mb-6">
          <div class="flex items-center mb-4">
            <div class="w-10 h-10 bg-purple-100 dark:bg-purple-900 rounded-lg flex items-center justify-center mr-3">
              <span class="text-lg">✍️</span>
            </div>
            <h3 class="text-xl font-semibold text-gray-900 dark:text-white">Typography System</h3>
          </div>
          <p class="text-gray-600 dark:text-gray-400">Consistent text hierarchy that works across all themes and modes</p>
        </div>

        <div class="space-y-6">
          <!-- Headings Demo -->
          <div>
            <h4 class="text-lg font-medium text-gray-900 dark:text-white mb-3">Heading Hierarchy</h4>
            <div class="space-y-2">
              <h1 class="text-3xl font-bold text-gray-900 dark:text-white">Heading 1</h1>
              <h2 class="text-2xl font-semibold text-gray-900 dark:text-white">Heading 2</h2>
              <h3 class="text-xl font-medium text-gray-900 dark:text-white">Heading 3</h3>
              <h4 class="text-lg text-gray-900 dark:text-white">Heading 4</h4>
            </div>
          </div>

          <!-- Body Text Demo -->
          <div>
            <h4 class="text-lg font-medium text-gray-900 dark:text-white mb-3">Body Text Styles</h4>
            <div class="space-y-3">
              <p class="text-base text-gray-900 dark:text-white">
                Primary text with optimal contrast for comfortable reading.
              </p>
              <p class="text-sm text-gray-600 dark:text-gray-400">
                Secondary text for supporting information and captions.
              </p>
              <p class="text-xs text-gray-500 dark:text-gray-500">
                Tertiary text for metadata and fine print.
              </p>
            </div>
          </div>

          <!-- Links Demo -->
          <div>
            <h4 class="text-lg font-medium text-gray-900 dark:text-white mb-3">Interactive Text</h4>
            <p class="text-gray-900 dark:text-white">
              This text contains a <a href="/themes" class="text-{currentTheme}-600 hover:text-{currentTheme}-700 dark:text-{currentTheme}-400 dark:hover:text-{currentTheme}-300 underline">themed link</a>, 
              <strong class="font-semibold">bold emphasis</strong>, and 
              <code class="px-2 py-1 text-sm bg-gray-100 dark:bg-gray-700 rounded">inline code</code>.
            </p>
          </div>
        </div>
      </Card>

      <!-- Dark Mode Showcase -->
      <Card class="p-8 bg-white dark:bg-gray-800 border border-gray-200 dark:border-gray-700 rounded-lg shadow-sm">
        <div class="mb-6">
          <div class="flex items-center mb-4">
            <div class="w-10 h-10 bg-gray-100 dark:bg-gray-700 rounded-lg flex items-center justify-center mr-3">
              <span class="text-lg">🌙</span>
            </div>
            <h3 class="text-xl font-semibold text-gray-900 dark:text-white">Dark Mode Excellence</h3>
          </div>
          <p class="text-gray-600 dark:text-gray-400">All themes maintain accessibility and visual appeal in both light and dark modes</p>
        </div>

        <div class="space-y-6">
          <!-- Dark Mode Features -->
          <div>
            <h4 class="text-lg font-medium text-gray-900 dark:text-white mb-3">Dark Mode Features</h4>
            <ul class="space-y-2 text-gray-600 dark:text-gray-300">
              <li class="flex items-start">
                <span class="text-green-500 mr-3 mt-1">✓</span>
                <span><strong>Automatic detection:</strong> Respects system preferences</span>
              </li>
              <li class="flex items-start">
                <span class="text-green-500 mr-3 mt-1">✓</span>
                <span><strong>Persistent choice:</strong> Remembers user selection</span>
              </li>
              <li class="flex items-start">
                <span class="text-green-500 mr-3 mt-1">✓</span>
                <span><strong>Theme compatibility:</strong> All colors work in both modes</span>
              </li>
              <li class="flex items-start">
                <span class="text-green-500 mr-3 mt-1">✓</span>
                <span><strong>Reduced eye strain:</strong> Lower contrast for dark environments</span>
              </li>
            </ul>
          </div>

          <!-- Color Contrast Demo -->
          <div>
            <h4 class="text-lg font-medium text-gray-900 dark:text-white mb-3">Contrast Examples</h4>
            <div class="space-y-3">
              <div class="p-3 bg-gray-100 dark:bg-gray-700 rounded">
                <span class="text-sm text-gray-600 dark:text-gray-300">Surface contrast</span>
              </div>
              <div class="p-3 bg-{currentTheme}-100 dark:bg-{currentTheme}-900/30 rounded border border-{currentTheme}-200 dark:border-{currentTheme}-800">
                <span class="text-sm text-{currentTheme}-700 dark:text-{currentTheme}-300">Themed surface contrast</span>
              </div>
              <div class="flex gap-2">
                <Button color={currentTheme} size="sm">Primary Action</Button>
                <Button color={currentTheme} outline size="sm">Secondary</Button>
              </div>
            </div>
          </div>
        </div>
      </Card>
    </div>

    <!-- Feature Summary Cards - 3-column responsive grid -->
    <div class="grid grid-cols-1 lg:grid-cols-3 gap-6 xl:gap-8 mb-16">
      <Card class="p-6 bg-gradient-to-br from-blue-50 to-blue-100 dark:from-blue-900/20 dark:to-blue-800/20 border border-blue-200 dark:border-blue-800 rounded-lg hover:shadow-md transition-all duration-200">
        <div class="flex items-center mb-4">
          <div class="w-12 h-12 bg-blue-100 dark:bg-blue-900 rounded-lg flex items-center justify-center mr-4">
            <span class="text-2xl">🎨</span>
          </div>
          <h3 class="text-xl font-semibold text-gray-900 dark:text-white">Dynamic Theming</h3>
        </div>
        <p class="text-gray-600 dark:text-gray-300 mb-4 leading-relaxed">
          Real-time theme switching with semantic color meanings and instant visual feedback across all components.
        </p>
        <Badge color="blue">Interactive</Badge>
      </Card>

      <Card class="p-6 bg-gradient-to-br from-purple-50 to-purple-100 dark:from-purple-900/20 dark:to-purple-800/20 border border-purple-200 dark:border-purple-800 rounded-lg hover:shadow-md transition-all duration-200">
        <div class="flex items-center mb-4">
          <div class="w-12 h-12 bg-purple-100 dark:bg-purple-900 rounded-lg flex items-center justify-center mr-4">
            <span class="text-2xl">🌓</span>
          </div>
          <h3 class="text-xl font-semibold text-gray-900 dark:text-white">Dark Mode Ready</h3>
        </div>
        <p class="text-gray-600 dark:text-gray-300 mb-4 leading-relaxed">
          Comprehensive dark mode support with proper contrast ratios and automatic system preference detection.
        </p>
        <Badge color="purple">Accessibility</Badge>
      </Card>

      <Card class="p-6 bg-gradient-to-br from-green-50 to-green-100 dark:from-green-900/20 dark:to-green-800/20 border border-green-200 dark:border-green-800 rounded-lg hover:shadow-md transition-all duration-200">
        <div class="flex items-center mb-4">
          <div class="w-12 h-12 bg-green-100 dark:bg-green-900 rounded-lg flex items-center justify-center mr-4">
            <span class="text-2xl">⚡</span>
          </div>
          <h3 class="text-xl font-semibold text-gray-900 dark:text-white">Production Ready</h3>
        </div>
        <p class="text-gray-600 dark:text-gray-300 mb-4 leading-relaxed">
          Enterprise-grade theming system with consistent design tokens and scalable color management.
        </p>
        <Badge color="green">Enterprise</Badge>
      </Card>
    </div>

    <!-- Footer Note -->
    <div class="text-center py-8">
      <div class="max-w-3xl mx-auto">
        <p class="text-gray-600 dark:text-gray-400 text-lg leading-relaxed">
          This theming system demonstrates the power of Flowbite Svelte's design token architecture. 
          All themes maintain WCAG AA accessibility standards and work seamlessly across light and dark modes 
          for professional application development.
        </p>
      </div>
    </div>

  </div>
</div>