<!-- src/routes/components/+page.svelte -->

<script>
  import { 
    Button, 
    Card, 
    Badge, 
    Input, 
    Label, 
    Textarea,
    Checkbox,
    Radio,
    Select,
    Toggle,
    Alert,
    Modal,
    Spinner,
    Avatar,
    Breadcrumb,
    BreadcrumbItem
  } from 'flowbite-svelte';
  // Import only verified available Flowbite Svelte icons
  import { CheckCircleSolid, CloseCircleSolid } from 'flowbite-svelte-icons';

  let checkboxValue = false;
  let radioValue = 'option1';
  let selectValue = '';
  let toggleValue = false;
  let modalOpen = false;

  const selectOptions = [
    { value: 'us', name: 'United States' },
    { value: 'ca', name: 'Canada' },
    { value: 'uk', name: 'United Kingdom' },
    { value: 'de', name: 'Germany' }
  ];
</script>

<svelte:head>
  <title>Components Demo - Flowbite Svelte</title>
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
          <BreadcrumbItem>Components</BreadcrumbItem>
        </Breadcrumb>
      </div>

      <div class="text-center">
        <h1 class="text-4xl lg:text-5xl font-bold tracking-tight text-gray-900 dark:text-white mb-4">
          Flowbite Svelte Components Demo
        </h1>
        <p class="text-xl text-gray-600 dark:text-gray-300 mb-8 max-w-3xl mx-auto">
          Explore our comprehensive collection of production-ready UI components with responsive design and proper accessibility
        </p>

        <!-- Technology Badges -->
        <div class="flex gap-3 justify-center flex-wrap">
          <Badge color="blue" class="text-sm px-3 py-1.5">Interactive Components</Badge>
          <Badge color="green" class="text-sm px-3 py-1.5">Responsive Design</Badge>
          <Badge color="purple" class="text-sm px-3 py-1.5">Dark Mode Ready</Badge>
          <Badge color="orange" class="text-sm px-3 py-1.5">Accessibility First</Badge>
        </div>
      </div>
    </div>
  </div>

  <!-- Main Content Area -->
  <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-12">

    <!-- Page Design Comments Card -->
    <div class="mb-16">
      <Card class="p-8 bg-gradient-to-br from-blue-50 to-indigo-100 dark:from-blue-900/20 dark:to-indigo-900/20 border border-blue-200 dark:border-blue-800 rounded-lg shadow-sm">
        <div class="flex items-start mb-6">
          <div class="w-12 h-12 bg-blue-100 dark:bg-blue-900 rounded-lg flex items-center justify-center mr-4 flex-shrink-0">
            <span class="text-2xl">💡</span>
          </div>
          <div>
            <h2 class="text-2xl font-bold text-gray-900 dark:text-white mb-2">Page Design Comments</h2>
            <p class="text-gray-600 dark:text-gray-300">Professional layout principles applied to component demonstration</p>
          </div>
        </div>

        <div class="grid grid-cols-1 lg:grid-cols-2 gap-8">
          <div>
            <h3 class="text-lg font-semibold text-gray-900 dark:text-white mb-4">Design Principles Applied</h3>
            <ul class="space-y-2 text-gray-600 dark:text-gray-300">
              <li class="flex items-start">
                <span class="text-green-500 mr-3 mt-1">✓</span>
                <span><strong>Equal-height cards</strong> for visual harmony and balanced grid layouts</span>
              </li>
              <li class="flex items-start">
                <span class="text-green-500 mr-3 mt-1">✓</span>
                <span><strong>Consistent spacing</strong> using systematic gap-6 and gap-8 measurements</span>
              </li>
              <li class="flex items-start">
                <span class="text-green-500 mr-3 mt-1">✓</span>
                <span><strong>Responsive breakpoints</strong> ensuring mobile-first progressive enhancement</span>
              </li>
              <li class="flex items-start">
                <span class="text-green-500 mr-3 mt-1">✓</span>
                <span><strong>Semantic color coding</strong> with meaningful gradients and hover states</span>
              </li>
            </ul>
          </div>

          <div>
            <h3 class="text-lg font-semibold text-gray-900 dark:text-white mb-4">What You're Seeing</h3>
            <ul class="space-y-2 text-gray-600 dark:text-gray-300">
              <li class="flex items-start">
                <span class="text-blue-500 mr-3 mt-1">▶</span>
                <span>Components organized in <strong>balanced pairs</strong> and logical groupings</span>
              </li>
              <li class="flex items-start">
                <span class="text-blue-500 mr-3 mt-1">▶</span>
                <span><strong>Professional grid system</strong> with proper max-width containers</span>
              </li>
              <li class="flex items-start">
                <span class="text-blue-500 mr-3 mt-1">▶</span>
                <span>Each section demonstrates <strong>real working components</strong> with interactive states</span>
              </li>
              <li class="flex items-start">
                <span class="text-blue-500 mr-3 mt-1">▶</span>
                <span><strong>Visual hierarchy</strong> using typography, spacing, and subtle gradients</span>
              </li>
            </ul>
          </div>
        </div>
      </Card>
    </div>

    <!-- Buttons & Badges Section - Equal height paired cards -->
    <div class="grid grid-cols-1 xl:grid-cols-2 gap-8 mb-16">
      
      <Card class="p-8 bg-white dark:bg-gray-800 border border-gray-200 dark:border-gray-700 rounded-lg shadow-sm">
        <div class="mb-6">
          <div class="flex items-center mb-4">
            <div class="w-10 h-10 bg-blue-100 dark:bg-blue-900 rounded-lg flex items-center justify-center mr-3">
              <span class="text-lg">🔘</span>
            </div>
            <h2 class="text-2xl font-bold text-gray-900 dark:text-white">Buttons</h2>
          </div>
          <p class="text-gray-600 dark:text-gray-400">Interactive button components with multiple variants and hover effects</p>
        </div>

        <div class="space-y-6">
          <div>
            <h3 class="text-lg font-semibold text-gray-900 dark:text-white mb-4">Primary Colors</h3>
            <div class="flex flex-wrap gap-3">
              <Button>Default</Button>
              <Button color="blue">Blue</Button>
              <Button color="green">Green</Button>
              <Button color="red">Red</Button>
              <Button color="yellow">Yellow</Button>
              <Button color="purple">Purple</Button>
            </div>
          </div>

          <div>
            <h3 class="text-lg font-semibold text-gray-900 dark:text-white mb-4">Variants & Sizes</h3>
            <div class="space-y-3">
              <div class="flex flex-wrap gap-3">
                <Button color="alternative">Alternative</Button>
                <Button color="dark">Dark</Button>
                <Button outline>Outline</Button>
                <Button color="blue" outline>Blue Outline</Button>
              </div>
              <div class="flex flex-wrap items-center gap-3">
                <Button size="xs">Extra Small</Button>
                <Button size="sm">Small</Button>
                <Button>Default</Button>
                <Button size="lg">Large</Button>
              </div>
            </div>
          </div>
        </div>
      </Card>

      <Card class="p-8 bg-white dark:bg-gray-800 border border-gray-200 dark:border-gray-700 rounded-lg shadow-sm">
        <div class="mb-6">
          <div class="flex items-center mb-4">
            <div class="w-10 h-10 bg-green-100 dark:bg-green-900 rounded-lg flex items-center justify-center mr-3">
              <span class="text-lg">🏷️</span>
            </div>
            <h2 class="text-2xl font-bold text-gray-900 dark:text-white">Badges</h2>
          </div>
          <p class="text-gray-600 dark:text-gray-400">Status indicators and category labels with semantic color coding</p>
        </div>

        <div class="space-y-6">
          <div>
            <h3 class="text-lg font-semibold text-gray-900 dark:text-white mb-4">Standard Badges</h3>
            <div class="flex flex-wrap gap-2">
              <Badge>Default</Badge>
              <Badge color="blue">Information</Badge>
              <Badge color="green">Success</Badge>
              <Badge color="red">Error</Badge>
              <Badge color="yellow">Warning</Badge>
              <Badge color="purple">Feature</Badge>
            </div>
          </div>

          <div>
            <h3 class="text-lg font-semibold text-gray-900 dark:text-white mb-4">Large Status Badges</h3>
            <div class="space-y-3">
              <div class="flex flex-wrap gap-3">
                <Badge color="green" large>✓ Completed</Badge>
                <Badge color="blue" large>ℹ Processing</Badge>
              </div>
              <div class="flex flex-wrap gap-3">
                <Badge color="yellow" large>⚠ Pending</Badge>
                <Badge color="red" large>✗ Failed</Badge>
              </div>
            </div>
          </div>
        </div>
      </Card>
    </div>

    <!-- Alerts & Form Inputs Section - Equal height paired cards -->
    <div class="grid grid-cols-1 xl:grid-cols-2 gap-8 mb-16">
      
      <Card class="p-8 bg-white dark:bg-gray-800 border border-gray-200 dark:border-gray-700 rounded-lg shadow-sm">
        <div class="mb-6">
          <div class="flex items-center mb-4">
            <div class="w-10 h-10 bg-yellow-100 dark:bg-yellow-900 rounded-lg flex items-center justify-center mr-3">
              <span class="text-lg">⚠️</span>
            </div>
            <h2 class="text-2xl font-bold text-gray-900 dark:text-white">Alerts</h2>
          </div>
          <p class="text-gray-600 dark:text-gray-400">User feedback messages with semantic styling and proper contrast</p>
        </div>

        <div class="space-y-4">
          <Alert color="blue">
            <span class="font-medium">Information:</span> Here's some helpful information about your request.
          </Alert>

          <Alert color="green">
            {#snippet icon()}<CheckCircleSolid class="h-5 w-5" />{/snippet}
            <span class="font-medium">Success:</span> Your changes have been saved successfully.
          </Alert>

          <Alert color="yellow">
            <span class="font-medium">Warning:</span> Please review your information before proceeding.
          </Alert>

          <Alert color="red">
            {#snippet icon()}<CloseCircleSolid class="h-5 w-5" />{/snippet}
            <span class="font-medium">Error:</span> Something went wrong. Please try again.
          </Alert>
        </div>
      </Card>

      <Card class="p-8 bg-white dark:bg-gray-800 border border-gray-200 dark:border-gray-700 rounded-lg shadow-sm">
        <div class="mb-6">
          <div class="flex items-center mb-4">
            <div class="w-10 h-10 bg-purple-100 dark:bg-purple-900 rounded-lg flex items-center justify-center mr-3">
              <span class="text-lg">📝</span>
            </div>
            <h2 class="text-2xl font-bold text-gray-900 dark:text-white">Form Inputs</h2>
          </div>
          <p class="text-gray-600 dark:text-gray-400">Essential form controls with proper validation styling and accessibility</p>
        </div>

        <div class="space-y-4">
          <div>
            <Label for="demo-text" class="mb-2">Text Input</Label>
            <Input id="demo-text" placeholder="Enter your text here" class="w-full" />
          </div>

          <div>
            <Label for="demo-email" class="mb-2">Email Address</Label>
            <Input id="demo-email" type="email" placeholder="your.email@example.com" class="w-full" />
          </div>

          <div>
            <Label for="demo-select" class="mb-2">Select Country</Label>
            <Select id="demo-select" bind:value={selectValue} items={selectOptions} placeholder="Choose a country" class="w-full" />
          </div>

          <div>
            <Label for="demo-textarea" class="mb-2">Message</Label>
            <Textarea id="demo-textarea" placeholder="Write your message here..." rows="3" class="w-full" />
          </div>
        </div>
      </Card>
    </div>

    <!-- Interactive Controls & Loading States Section - Equal height paired cards -->
    <div class="grid grid-cols-1 xl:grid-cols-2 gap-8 mb-16">
      
      <Card class="p-8 bg-white dark:bg-gray-800 border border-gray-200 dark:border-gray-700 rounded-lg shadow-sm">
        <div class="mb-6">
          <div class="flex items-center mb-4">
            <div class="w-10 h-10 bg-indigo-100 dark:bg-indigo-900 rounded-lg flex items-center justify-center mr-3">
              <span class="text-lg">🎛️</span>
            </div>
            <h2 class="text-2xl font-bold text-gray-900 dark:text-white">Interactive Controls</h2>
          </div>
          <p class="text-gray-600 dark:text-gray-400">User input controls with proper state management and accessibility</p>
        </div>

        <div class="space-y-6">
          <div>
            <h3 class="text-lg font-semibold text-gray-900 dark:text-white mb-3">Checkboxes</h3>
            <div class="space-y-2">
              <Checkbox bind:checked={checkboxValue}>I agree to the terms and conditions</Checkbox>
              <Checkbox>Send me marketing emails</Checkbox>
              <Checkbox checked disabled>This option is disabled</Checkbox>
            </div>
          </div>

          <div>
            <h3 class="text-lg font-semibold text-gray-900 dark:text-white mb-3">Radio Buttons</h3>
            <div class="space-y-2">
              <Radio name="demo-options" bind:group={radioValue} value="option1">Payment Option 1</Radio>
              <Radio name="demo-options" bind:group={radioValue} value="option2">Payment Option 2</Radio>
              <Radio name="demo-options" bind:group={radioValue} value="option3">Payment Option 3</Radio>
            </div>
          </div>

          <div>
            <h3 class="text-lg font-semibold text-gray-900 dark:text-white mb-3">Toggle Switch</h3>
            <Toggle bind:checked={toggleValue}>Enable notifications</Toggle>
          </div>
        </div>
      </Card>

      <Card class="p-8 bg-white dark:bg-gray-800 border border-gray-200 dark:border-gray-700 rounded-lg shadow-sm">
        <div class="mb-6">
          <div class="flex items-center mb-4">
            <div class="w-10 h-10 bg-cyan-100 dark:bg-cyan-900 rounded-lg flex items-center justify-center mr-3">
              <span class="text-lg">⏳</span>
            </div>
            <h2 class="text-2xl font-bold text-gray-900 dark:text-white">Loading & Media</h2>
          </div>
          <p class="text-gray-600 dark:text-gray-400">Progress indicators, spinners, and user representation components</p>
        </div>

        <div class="space-y-6">
          <div>
            <h3 class="text-lg font-semibold text-gray-900 dark:text-white mb-3">Progress Bars</h3>
            <div class="space-y-4">
              <div>
                <div class="flex justify-between mb-2">
                  <span class="text-sm font-medium text-blue-700 dark:text-blue-400">Upload Progress</span>
                  <span class="text-sm font-medium text-blue-700 dark:text-blue-400">68%</span>
                </div>
                <div class="w-full bg-gray-200 rounded-full h-2.5 dark:bg-gray-700">
                  <div class="bg-blue-600 h-2.5 rounded-full transition-all duration-300" style="width: 68%"></div>
                </div>
              </div>
              
              <div>
                <div class="flex justify-between mb-2">
                  <span class="text-sm font-medium text-green-700 dark:text-green-400">Processing</span>
                  <span class="text-sm font-medium text-green-700 dark:text-green-400">85%</span>
                </div>
                <div class="w-full bg-gray-200 rounded-full h-2.5 dark:bg-gray-700">
                  <div class="bg-green-600 h-2.5 rounded-full transition-all duration-300" style="width: 85%"></div>
                </div>
              </div>
            </div>
          </div>

          <div>
            <h3 class="text-lg font-semibold text-gray-900 dark:text-white mb-3">Spinners & Avatars</h3>
            <div class="space-y-4">
              <div class="flex gap-4 items-center">
                <div class="text-center">
                  <Spinner size="4" />
                  <span class="text-xs text-gray-500 dark:text-gray-400 mt-1 block">Small</span>
                </div>
                <div class="text-center">
                  <Spinner size="6" color="blue" />
                  <span class="text-xs text-gray-500 dark:text-gray-400 mt-1 block">Medium</span>
                </div>
                <div class="text-center">
                  <Spinner size="8" color="green" />
                  <span class="text-xs text-gray-500 dark:text-gray-400 mt-1 block">Large</span>
                </div>
              </div>

              <div class="flex gap-3 items-center">
                <Avatar />
                <Avatar src="https://flowbite.com/docs/images/people/profile-picture-1.jpg" />
                <Avatar src="https://flowbite.com/docs/images/people/profile-picture-2.jpg" size="lg" />
                <Button on:click={() => modalOpen = true} size="sm">Open Modal</Button>
              </div>
            </div>
          </div>
        </div>

        <Modal bind:open={modalOpen} title="Component Demo Modal">
          <p class="text-base leading-relaxed text-gray-500 dark:text-gray-400">
            This modal demonstrates proper focus management and keyboard navigation support for accessibility.
            It includes proper ARIA labels and can be closed with the Escape key.
          </p>
          <div slot="footer" class="flex space-x-2">
            <Button on:click={() => modalOpen = false}>Confirm</Button>
            <Button color="alternative" on:click={() => modalOpen = false}>Cancel</Button>
          </div>
        </Modal>
      </Card>
    </div>

    <!-- Feature Summary Cards - 3-column responsive grid -->
    <div class="grid grid-cols-1 lg:grid-cols-3 gap-6 xl:gap-8 mb-16">
      <Card class="p-6 bg-gradient-to-br from-blue-50 to-blue-100 dark:from-blue-900/20 dark:to-blue-800/20 border border-blue-200 dark:border-blue-800 rounded-lg hover:shadow-md transition-all duration-200">
        <div class="flex items-center mb-4">
          <div class="w-12 h-12 bg-blue-100 dark:bg-blue-900 rounded-lg flex items-center justify-center mr-4">
            <span class="text-2xl">⚡</span>
          </div>
          <h3 class="text-xl font-semibold text-gray-900 dark:text-white">Fast Development</h3>
        </div>
        <p class="text-gray-600 dark:text-gray-300 mb-4 leading-relaxed">
          Components that work seamlessly with Svelte 5 and modern development practices for rapid prototyping.
        </p>
        <Badge color="blue">Performance</Badge>
      </Card>

      <Card class="p-6 bg-gradient-to-br from-green-50 to-green-100 dark:from-green-900/20 dark:to-green-800/20 border border-green-200 dark:border-green-800 rounded-lg hover:shadow-md transition-all duration-200">
        <div class="flex items-center mb-4">
          <div class="w-12 h-12 bg-green-100 dark:bg-green-900 rounded-lg flex items-center justify-center mr-4">
            <span class="text-2xl">🎨</span>
          </div>
          <h3 class="text-xl font-semibold text-gray-900 dark:text-white">Modern Styling</h3>
        </div>
        <p class="text-gray-600 dark:text-gray-300 mb-4 leading-relaxed">
          Beautiful components that adapt seamlessly to both light and dark themes with consistent design language.
        </p>
        <Badge color="green">Design</Badge>
      </Card>

      <Card class="p-6 bg-gradient-to-br from-purple-50 to-purple-100 dark:from-purple-900/20 dark:to-purple-800/20 border border-purple-200 dark:border-purple-800 rounded-lg hover:shadow-md transition-all duration-200">
        <div class="flex items-center mb-4">
          <div class="w-12 h-12 bg-purple-100 dark:bg-purple-900 rounded-lg flex items-center justify-center mr-4">
            <span class="text-2xl">♿</span>
          </div>
          <h3 class="text-xl font-semibold text-gray-900 dark:text-white">Accessible</h3>
        </div>
        <p class="text-gray-600 dark:text-gray-300 mb-4 leading-relaxed">
          All components follow WCAG guidelines with proper ARIA labels, keyboard navigation, and screen reader support.
        </p>
        <Badge color="purple">Inclusive</Badge>
      </Card>
    </div>

    <!-- Footer Note -->
    <div class="text-center py-8">
      <div class="max-w-3xl mx-auto">
        <p class="text-gray-600 dark:text-gray-400 text-lg leading-relaxed">
          All components are fully responsive and work seamlessly with Svelte 5 and Tailwind CSS v4. 
          This page demonstrates balanced layout principles with equal-height cards and proper visual hierarchy 
          for professional web applications.
        </p>
      </div>
    </div>

  </div>
</div>