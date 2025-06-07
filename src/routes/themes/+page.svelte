<script>
  import { 
    Button, 
    Card, 
    Badge, 
    Input, 
    Label,
    Breadcrumb,
    BreadcrumbItem,
    Alert
  } from 'flowbite-svelte';
  import { toggleDarkMode } from '$lib/utils';
  import { InfoCircleSolid } from 'flowbite-svelte-icons';

  let currentTheme = 'blue';

  const themes = [
    { name: 'Blue', value: 'blue', class: 'bg-blue-600' },
    { name: 'Green', value: 'green', class: 'bg-green-600' },
    { name: 'Red', value: 'red', class: 'bg-red-600' },
    { name: 'Purple', value: 'purple', class: 'bg-purple-600' },
    { name: 'Yellow', value: 'yellow', class: 'bg-yellow-500' },
    { name: 'Pink', value: 'pink', class: 'bg-pink-600' },
  ];

  function applyTheme(theme) {
    currentTheme = theme;
    // In a real app, you could update CSS custom properties here
    document.documentElement.style.setProperty('--primary-color', getComputedStyle(document.documentElement).getPropertyValue(`--${theme}-600`));
  }
</script>

<svelte:head>
  <title>Themes Demo - Flowbite Svelte</title>
</svelte:head>

<div class="container mx-auto px-4 py-8">
  <!-- Breadcrumb -->
  <Breadcrumb class="mb-6">
    <BreadcrumbItem href="/" home>Home</BreadcrumbItem>
    <BreadcrumbItem>Themes</BreadcrumbItem>
  </Breadcrumb>

  <div class="text-center mb-12">
    <h1 class="text-3xl font-bold text-gray-900 dark:text-white mb-4">
      Flowbite Svelte Themes Demo
    </h1>
    <p class="text-xl text-gray-600 dark:text-gray-400 mb-6">
      Explore color themes and dark mode capabilities
    </p>

    <!-- Dark Mode Toggle -->
    <Button on:click={toggleDarkMode} color="alternative" class="gap-2 mb-6">
      <span class="dark:hidden">🌙 Dark Mode</span>
      <span class="hidden dark:inline">☀️ Light Mode</span>
    </Button>
  </div>

  <!-- Theme Selection -->
  <Card class="max-w-4xl mx-auto mb-8">
    <h2 class="text-2xl font-semibold text-gray-900 dark:text-white mb-4">Color Themes</h2>
    <p class="text-gray-600 dark:text-gray-400 mb-6">
      Flowbite Svelte supports multiple color schemes out of the box
    </p>

    <div class="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-6 gap-4">
      {#each themes as theme}
        <button
          class="flex flex-col items-center p-4 border-2 rounded-lg transition-all duration-200 hover:shadow-lg {currentTheme === theme.value ? 'border-primary-600 bg-primary-50 dark:bg-primary-900/20' : 'border-gray-200 dark:border-gray-700 hover:border-gray-300 dark:hover:border-gray-600'}"
          on:click={() => applyTheme(theme.value)}
        >
          <div class="w-12 h-12 {theme.class} rounded-full mb-3"></div>
          <span class="text-sm font-medium text-gray-900 dark:text-white">{theme.name}</span>
        </button>
      {/each}
    </div>
  </Card>

  <!-- Live Demo Section -->
  <div class="grid gap-8 lg:grid-cols-2 mb-8">
    <!-- Interactive Components -->
    <Card class="max-w-none">
      <h3 class="text-xl font-semibold text-gray-900 dark:text-white mb-4">Interactive Elements</h3>
      <p class="text-gray-600 dark:text-gray-400 mb-6">
        Components using the current theme with proper hover effects
      </p>

      <div class="space-y-6">
        <!-- Buttons in Current Theme -->
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

        <!-- Badges in Current Theme -->
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

        <!-- Form Elements -->
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

    <!-- Color Palette -->
    <Card class="max-w-none">
      <h3 class="text-xl font-semibold text-gray-900 dark:text-white mb-4">Color Palette</h3>
      <p class="text-gray-600 dark:text-gray-400 mb-6">
        Current theme color variations and shades
      </p>

      <div class="space-y-4">
        <!-- Current Theme Colors -->
        <div>
          <Label class="text-sm font-medium text-gray-900 dark:text-white mb-3">
            {themes.find(t => t.value === currentTheme)?.name} Theme
          </Label>
          <div class="grid grid-cols-5 gap-2">
            <div class="space-y-1">
              <div class="w-full h-12 bg-{currentTheme}-100 rounded border"></div>
              <span class="text-xs text-gray-600 dark:text-gray-400">100</span>
            </div>
            <div class="space-y-1">
              <div class="w-full h-12 bg-{currentTheme}-300 rounded border"></div>
              <span class="text-xs text-gray-600 dark:text-gray-400">300</span>
            </div>
            <div class="space-y-1">
              <div class="w-full h-12 bg-{currentTheme}-500 rounded border"></div>
              <span class="text-xs text-gray-600 dark:text-gray-400">500</span>
            </div>
            <div class="space-y-1">
              <div class="w-full h-12 bg-{currentTheme}-700 rounded border"></div>
              <span class="text-xs text-gray-600 dark:text-gray-400">700</span>
            </div>
            <div class="space-y-1">
              <div class="w-full h-12 bg-{currentTheme}-900 rounded border"></div>
              <span class="text-xs text-gray-600 dark:text-gray-400">900</span>
            </div>
          </div>
        </div>

        <!-- Neutral Colors -->
        <div>
          <Label class="text-sm font-medium text-gray-900 dark:text-white mb-3">
            Neutral Colors
          </Label>
          <div class="grid grid-cols-5 gap-2">
            <div class="space-y-1">
              <div class="w-full h-12 bg-gray-100 dark:bg-gray-800 rounded border"></div>
              <span class="text-xs text-gray-600 dark:text-gray-400">Light</span>
            </div>
            <div class="space-y-1">
              <div class="w-full h-12 bg-gray-300 dark:bg-gray-600 rounded border"></div>
              <span class="text-xs text-gray-600 dark:text-gray-400">Medium</span>
            </div>
            <div class="space-y-1">
              <div class="w-full h-12 bg-gray-500 rounded border"></div>
              <span class="text-xs text-gray-600 dark:text-gray-400">Base</span>
            </div>
            <div class="space-y-1">
              <div class="w-full h-12 bg-gray-700 dark:bg-gray-300 rounded border"></div>
              <span class="text-xs text-gray-600 dark:text-gray-400">Dark</span>
            </div>
            <div class="space-y-1">
              <div class="w-full h-12 bg-gray-900 dark:bg-gray-100 rounded border"></div>
              <span class="text-xs text-gray-600 dark:text-gray-400">Darkest</span>
            </div>
          </div>
        </div>
      </div>
    </Card>
  </div>

  <!-- Status Indicators -->
  <Card class="max-w-4xl mx-auto mb-8">
    <h3 class="text-xl font-semibold text-gray-900 dark:text-white mb-4">Status System</h3>
    <p class="text-gray-600 dark:text-gray-400 mb-6">
      Semantic colors for different states and feedback
    </p>

    <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
      <!-- Alert States -->
      <div class="space-y-4">
        <h4 class="text-lg font-medium text-gray-900 dark:text-white">Alert States</h4>

        <Alert color="blue">
          <InfoCircleSolid slot="icon" class="w-4 h-4" />
          <span class="font-medium">Information:</span> Here's some helpful information for you.
        </Alert>

        <Alert color="green">
          <InfoCircleSolid slot="icon" class="w-4 h-4" />
          <span class="font-medium">Success:</span> Your action was completed successfully.
        </Alert>

        <Alert color="yellow">
          <InfoCircleSolid slot="icon" class="w-4 h-4" />
          <span class="font-medium">Warning:</span> Please review this information carefully.
        </Alert>

        <Alert color="red">
          <InfoCircleSolid slot="icon" class="w-4 h-4" />
          <span class="font-medium">Error:</span> Something went wrong. Please try again.
        </Alert>
      </div>

      <!-- Status Badges -->
      <div class="space-y-4">
        <h4 class="text-lg font-medium text-gray-900 dark:text-white">Status Badges</h4>

        <div class="space-y-3">
          <div class="flex items-center justify-between p-3 border border-gray-200 dark:border-gray-700 rounded-lg">
            <span class="text-gray-900 dark:text-white">System Status</span>
            <Badge color="green">Operational</Badge>
          </div>

          <div class="flex items-center justify-between p-3 border border-gray-200 dark:border-gray-700 rounded-lg">
            <span class="text-gray-900 dark:text-white">Database</span>
            <Badge color="yellow">Maintenance</Badge>
          </div>

          <div class="flex items-center justify-between p-3 border border-gray-200 dark:border-gray-700 rounded-lg">
            <span class="text-gray-900 dark:text-white">API Service</span>
            <Badge color="red">Down</Badge>
          </div>

          <div class="flex items-center justify-between p-3 border border-gray-200 dark:border-gray-700 rounded-lg">
            <span class="text-gray-900 dark:text-white">CDN</span>
            <Badge color="blue">Updating</Badge>
          </div>
        </div>
      </div>
    </div>
  </Card>

  <!-- Typography Showcase -->
  <Card class="max-w-4xl mx-auto">
    <h3 class="text-xl font-semibold text-gray-900 dark:text-white mb-4">Typography & Hierarchy</h3>
    <p class="text-gray-600 dark:text-gray-400 mb-6">
      Text styles that work well in both light and dark modes
    </p>

    <div class="space-y-6">
      <!-- Headings -->
      <div>
        <h4 class="text-lg font-medium text-gray-900 dark:text-white mb-3">Headings</h4>
        <div class="space-y-2">
          <h1 class="text-4xl font-bold text-gray-900 dark:text-white">Heading 1</h1>
          <h2 class="text-3xl font-semibold text-gray-900 dark:text-white">Heading 2</h2>
          <h3 class="text-2xl font-medium text-gray-900 dark:text-white">Heading 3</h3>
          <h4 class="text-xl text-gray-900 dark:text-white">Heading 4</h4>
        </div>
      </div>

      <!-- Body Text -->
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

      <!-- Links and Emphasis -->
      <div>
        <h4 class="text-lg font-medium text-gray-900 dark:text-white mb-3">Links & Emphasis</h4>
        <div class="space-y-2">
          <p class="text-gray-900 dark:text-white">
            This paragraph contains a <a href="#" class="text-{currentTheme}-600 hover:text-{currentTheme}-700 underline">themed link</a> and 
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