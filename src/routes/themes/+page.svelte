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
    { name: 'Blue', value: 'blue', class: 'bg-blue-600' },
    { name: 'Green', value: 'green', class: 'bg-green-600' },
    { name: 'Red', value: 'red', class: 'bg-red-600' },
    { name: 'Purple', value: 'purple', class: 'bg-purple-600' },
    { name: 'Yellow', value: 'yellow', class: 'bg-yellow-500' },
    { name: 'Pink', value: 'pink', class: 'bg-pink-600' },
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

<div class="container mx-auto px-4 py-8">
  <!-- Navigation breadcrumb -->
  <Breadcrumb class="mb-6">
    <BreadcrumbItem href="/" home>Home</BreadcrumbItem>
    <BreadcrumbItem>Themes</BreadcrumbItem>
  </Breadcrumb>

  <!-- Page header with title and dark mode toggle -->
  <div class="text-center mb-12">
    <h1 class="text-3xl font-bold text-gray-900 dark:text-white mb-4">
      Flowbite Svelte Themes Demo
    </h1>
    <p class="text-xl text-gray-600 dark:text-gray-400 mb-6">
      Explore color themes and dark mode capabilities
    </p>

    <!-- Official Flowbite Dark Mode Toggle -->
    <DarkMode class="gap-2 bg-gray-100 hover:bg-gray-200 text-gray-900 dark:bg-gray-700 dark:hover:bg-gray-600 dark:text-white border border-gray-300 dark:border-gray-600 px-4 py-2 rounded-lg mb-6" />
  </div>

  <!-- Theme Selection Section -->
  <Card class="max-w-4xl mx-auto mb-8 p-6 bg-white dark:bg-gray-800 border border-gray-200 dark:border-gray-700 rounded-lg shadow-sm">
    <h2 class="text-2xl font-semibold text-gray-900 dark:text-white mb-4">Color Themes</h2>
    <p class="text-gray-600 dark:text-gray-400 mb-6">
      Flowbite Svelte supports multiple color schemes out of the box
    </p>

    <!-- Theme selector grid -->
    <div class="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-6 gap-4">
      {#each themes as theme}
        <button
          class="flex flex-col items-center p-4 border-2 rounded-lg transition-all duration-200 hover:shadow-lg {currentTheme === theme.value ? 'border-primary-600 bg-primary-50 dark:bg-primary-900/20' : 'border-gray-200 dark:border-gray-700 hover:border-gray-300 dark:hover:border-gray-600'}"
          on:click={() => applyTheme(theme.value)}
        >
          <!-- Theme color circle -->
          <div class="w-12 h-12 {theme.class} rounded-full mb-3"></div>
          <!-- Theme name -->
          <span class="text-sm font-medium text-gray-900 dark:text-white">{theme.name}</span>
        </button>
      {/each}
    </div>
  </Card>

  <!-- Live Demo Section - Two column layout -->
  <div class="grid gap-8 lg:grid-cols-2 mb-8">
    
    <!-- Left Column: Interactive Components -->
    <Card class="p-6 bg-white dark:bg-gray-800 border border-gray-200 dark:border-gray-700 rounded-lg shadow-sm">
      <h3 class="text-xl font-semibold text-gray-900 dark:text-white mb-4">Interactive Elements</h3>
      <p class="text-gray-600 dark:text-gray-400 mb-6">
        Components using the current theme with proper hover effects
      </p>

      <div class="space-y-6">
        <!-- Themed Buttons Section -->
        <div>
          <Label class="text-sm font-medium text-gray-900 dark:text-white mb-3">
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
          <Label class="text-sm font-medium text-gray-900 dark:text-white mb-3">
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
          <Label class="text-sm font-medium text-gray-900 dark:text-white mb-3">
            Form Elements
          </Label>
          <div class="space-y-3">
            <Input placeholder="Themed input field" />
            <div class="flex gap-2">
              <Button color={currentTheme} size="sm">Submit</Button>
              <Button color="alternative" size="sm">Cancel</Button>
            </div>
          </div>
        </div>
      </div>
    </Card>

    <!-- Right Column: Status System -->
    <Card class="p-6 bg-white dark:bg-gray-800 border border-gray-200 dark:border-gray-700 rounded-lg shadow-sm">
      <h3 class="text-xl font-semibold text-gray-900 dark:text-white mb-4">Status System</h3>
      <p class="text-gray-600 dark:text-gray-400 mb-6">
        Semantic colors for different states and feedback
      </p>

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
          <span class="font-medium">Success:</span> Your action was completed successfully.
        </Alert>

        <!-- Warning Alert -->
        <Alert color="yellow">
          <svg slot="icon" class="w-4 h-4" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="currentColor" viewBox="0 0 20 20">
            <path d="M10 .5a9.5 9.5 0 1 0 9.5 9.5A9.51 9.51 0 0 0 10 .5ZM10 15a1 1 0 1 1 0-2 1 1 0 0 1 0 2Zm1-4a1 1 0 0 1-2 0V6a1 1 0 0 1 2 0v5Z"/>
          </svg>
          <span class="font-medium">Warning:</span> Please review this information carefully.
        </Alert>

        <!-- Error Alert -->
        <Alert color="red">
          <svg slot="icon" class="w-4 h-4" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="currentColor" viewBox="0 0 20 20">
            <path d="M10 .5a9.5 9.5 0 1 0 9.5 9.5A9.51 9.51 0 0 0 10 .5ZM10 15a1 1 0 1 1 0-2 1 1 0 0 1 0 2Zm1-4a1 1 0 0 1-2 0V6a1 1 0 0 1 2 0v5Z"/>
          </svg>
          <span class="font-medium">Error:</span> Something went wrong. Please try again.
        </Alert>
      </div>
    </Card>
  </div>

  <!-- Typography Showcase Section -->
  <Card class="max-w-4xl mx-auto p-6 bg-white dark:bg-gray-800 border border-gray-200 dark:border-gray-700 rounded-lg shadow-sm">
    <h3 class="text-xl font-semibold text-gray-900 dark:text-white mb-4">Typography & Hierarchy</h3>
    <p class="text-gray-600 dark:text-gray-400 mb-6">
      Text styles that work well in both light and dark modes
    </p>

    <div class="space-y-6">
      <!-- Headings Demo -->
      <div>
        <h4 class="text-lg font-medium text-gray-900 dark:text-white mb-3">Headings</h4>
        <div class="space-y-2">
          <h1 class="text-4xl font-bold text-gray-900 dark:text-white">Heading 1</h1>
          <h2 class="text-3xl font-semibold text-gray-900 dark:text-white">Heading 2</h2>
          <h3 class="text-2xl font-medium text-gray-900 dark:text-white">Heading 3</h3>
          <h4 class="text-xl text-gray-900 dark:text-white">Heading 4</h4>
        </div>
      </div>

      <!-- Body Text Demo -->
      <div>
        <h4 class="text-lg font-medium text-gray-900 dark:text-white mb-3">Body Text</h4>
        <div class="space-y-3">
          <p class="text-lg text-gray-900 dark:text-white">
            Large body text for introductions and important content.
          </p>
          <p class="text-base text-gray-900 dark:text-white">
            Regular paragraph text with proper contrast for comfortable reading in both light and dark modes.
          </p>
          <p class="text-sm text-gray-600 dark:text-gray-400">
            Small text for secondary information, captions, and helper text.
          </p>
          <p class="text-xs text-gray-500 dark:text-gray-500">
            Extra small text for fine print, timestamps, and metadata.
          </p>
        </div>
      </div>

      <!-- Links and Emphasis Demo -->
      <div>
        <h4 class="text-lg font-medium text-gray-900 dark:text-white mb-3">Links & Emphasis</h4>
        <div class="space-y-2">
          <p class="text-gray-900 dark:text-white">
            This paragraph contains a <a href="/themes" class="text-{currentTheme}-600 hover:text-{currentTheme}-700 underline">themed link</a> and 
            <strong class="font-semibold">bold text</strong> with proper styling.
          </p>
          <p class="text-gray-600 dark:text-gray-400">
            Secondary text with <em class="italic">italic emphasis</em> and 
            <code class="px-2 py-1 text-sm bg-gray-100 dark:bg-gray-800 rounded">inline code</code> styling.
          </p>
        </div>
      </div>
    </div>
  </Card>
</div>