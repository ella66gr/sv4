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

<div class="container mx-auto px-4 py-8">
  <!-- Breadcrumb -->
  <Breadcrumb class="mb-6">
    <BreadcrumbItem href="/" home>Home</BreadcrumbItem>
    <BreadcrumbItem>Components</BreadcrumbItem>
  </Breadcrumb>

  <h1 class="text-3xl font-bold text-gray-900 dark:text-white mb-8">
    Flowbite Svelte Components Demo
  </h1>

  <div class="grid gap-8">
    <!-- Buttons Section -->
    <Card class="p-6 bg-white dark:bg-gray-800 border border-gray-200 dark:border-gray-700 rounded-lg shadow-sm">
      <h2 class="text-xl font-semibold text-gray-900 dark:text-white mb-4">Buttons</h2>
      <p class="text-gray-600 dark:text-gray-400 mb-6">Various button styles and variants with working hover effects</p>

      <div class="space-y-4">
        <!-- Primary Buttons -->
        <div>
          <h3 class="text-lg font-medium text-gray-900 dark:text-white mb-3">Primary Buttons</h3>
          <div class="flex flex-wrap gap-3">
            <Button>Default</Button>
            <Button color="blue">Blue</Button>
            <Button color="green">Green</Button>
            <Button color="red">Red</Button>
            <Button color="yellow">Yellow</Button>
            <Button color="purple">Purple</Button>
          </div>
        </div>

        <!-- Button Variants -->
        <div>
          <h3 class="text-lg font-medium text-gray-900 dark:text-white mb-3">Button Variants</h3>
          <div class="flex flex-wrap gap-3">
            <Button color="alternative">Alternative</Button>
            <Button color="dark">Dark</Button>
            <Button color="light">Light</Button>
            <Button outline>Outline</Button>
            <Button color="blue" outline>Blue Outline</Button>
          </div>
        </div>

        <!-- Button Sizes -->
        <div>
          <h3 class="text-lg font-medium text-gray-900 dark:text-white mb-3">Button Sizes</h3>
          <div class="flex flex-wrap items-center gap-3">
            <Button size="xs">Extra Small</Button>
            <Button size="sm">Small</Button>
            <Button>Default</Button>
            <Button size="lg">Large</Button>
            <Button size="xl">Extra Large</Button>
          </div>
        </div>
      </div>
    </Card>

    <!-- Badges & Alerts -->
    <div class="grid grid-cols-1 lg:grid-cols-2 gap-8">
      <Card class="p-6 bg-white dark:bg-gray-800 border border-gray-200 dark:border-gray-700 rounded-lg shadow-sm">
        <h2 class="text-xl font-semibold text-gray-900 dark:text-white mb-4">Badges</h2>
        <p class="text-gray-600 dark:text-gray-400 mb-6">Colorful status and category indicators</p>

        <div class="space-y-4">
          <div>
            <h3 class="text-lg font-medium text-gray-900 dark:text-white mb-3">Default Badges</h3>
            <div class="flex flex-wrap gap-2">
              <Badge>Default</Badge>
              <Badge color="blue">Blue</Badge>
              <Badge color="green">Green</Badge>
              <Badge color="red">Red</Badge>
              <Badge color="yellow">Yellow</Badge>
              <Badge color="purple">Purple</Badge>
            </div>
          </div>

          <div>
            <h3 class="text-lg font-medium text-gray-900 dark:text-white mb-3">Large Badges</h3>
            <div class="flex flex-wrap gap-2">
              <Badge large>Default</Badge>
              <Badge color="green" large>Success</Badge>
              <Badge color="red" large>Error</Badge>
              <Badge color="yellow" large>Warning</Badge>
            </div>
          </div>
        </div>
      </Card>

      <Card class="p-6 bg-white dark:bg-gray-800 border border-gray-200 dark:border-gray-700 rounded-lg shadow-sm">
        <h2 class="text-xl font-semibold text-gray-900 dark:text-white mb-4">Alerts</h2>
        <p class="text-gray-600 dark:text-gray-400 mb-6">User feedback and notification messages</p>

        <div class="space-y-4">
          <!-- Following official Flowbite-Svelte documentation pattern -->
          <!-- Using simple alerts without icons to avoid import issues -->
          <Alert color="blue">
            <span class="font-medium">Info alert!</span> Change a few things up and try submitting again.
          </Alert>

          <Alert color="green">
            {#snippet icon()}<CheckCircleSolid class="h-5 w-5" />{/snippet}
            <span class="font-medium">Success alert!</span> Your changes have been saved successfully.
          </Alert>

          <Alert color="yellow">
            <span class="font-medium">Warning alert!</span> Please review your information before proceeding.
          </Alert>

          <Alert color="red">
            {#snippet icon()}<CloseCircleSolid class="h-5 w-5" />{/snippet}
            <span class="font-medium">Error alert!</span> Something went wrong. Please try again.
          </Alert>
        </div>
      </Card>
    </div>

    <!-- Form Components -->
    <Card class="p-6 bg-white dark:bg-gray-800 border border-gray-200 dark:border-gray-700 rounded-lg shadow-sm">
      <h2 class="text-xl font-semibold text-gray-900 dark:text-white mb-4">Form Components</h2>
      <p class="text-gray-600 dark:text-gray-400 mb-6">Interactive form controls with proper styling</p>

      <div class="grid grid-cols-1 lg:grid-cols-2 gap-8">
        <div class="space-y-6">
          <!-- Text Inputs -->
          <div>
            <Label for="text-input" class="mb-2">Text Input</Label>
            <Input id="text-input" placeholder="Enter text here" />
          </div>

          <div>
            <Label for="email-input" class="mb-2">Email Input</Label>
            <Input id="email-input" type="email" placeholder="your.email@example.com" />
          </div>

          <div>
            <Label for="textarea" class="mb-2">Textarea</Label>
            <Textarea id="textarea" placeholder="Write your message here..." rows="4" />
          </div>

          <!-- Select -->
          <div>
            <Label for="select" class="mb-2">Select Country</Label>
            <Select id="select" bind:value={selectValue} items={selectOptions} placeholder="Choose a country" />
          </div>
        </div>

        <div class="space-y-6">
          <!-- Checkboxes -->
          <div>
            <h3 class="text-lg font-medium text-gray-900 dark:text-white mb-3">Checkboxes</h3>
            <div class="space-y-3">
              <Checkbox bind:checked={checkboxValue}>I agree to the terms and conditions</Checkbox>
              <Checkbox>Send me marketing emails</Checkbox>
              <Checkbox checked disabled>This option is disabled</Checkbox>
            </div>
          </div>

          <!-- Radio Buttons -->
          <div>
            <h3 class="text-lg font-medium text-gray-900 dark:text-white mb-3">Radio Buttons</h3>
            <div class="space-y-3">
              <Radio name="options" bind:group={radioValue} value="option1">Option 1</Radio>
              <Radio name="options" bind:group={radioValue} value="option2">Option 2</Radio>
              <Radio name="options" bind:group={radioValue} value="option3">Option 3</Radio>
            </div>
          </div>

          <!-- Toggle -->
          <div>
            <h3 class="text-lg font-medium text-gray-900 dark:text-white mb-3">Toggle Switch</h3>
            <Toggle bind:checked={toggleValue}>Enable notifications</Toggle>
          </div>
        </div>
      </div>
    </Card>

    <!-- Loading & Interactive -->
    <div class="grid grid-cols-1 lg:grid-cols-2 gap-8">
      <Card class="p-6 bg-white dark:bg-gray-800 border border-gray-200 dark:border-gray-700 rounded-lg shadow-sm">
        <h2 class="text-xl font-semibold text-gray-900 dark:text-white mb-4">Loading Indicators</h2>
        <p class="text-gray-600 dark:text-gray-400 mb-6">Visual feedback for loading states</p>

        <div class="space-y-6">
          <div>
            <h3 class="text-lg font-medium text-gray-900 dark:text-white mb-3">Progress Bars</h3>
            <div class="space-y-4">
              <!-- Custom progress bars using Tailwind CSS -->
              <div>
                <div class="flex justify-between mb-1">
                  <span class="text-sm font-medium text-blue-700 dark:text-white">Progress</span>
                  <span class="text-sm font-medium text-blue-700 dark:text-white">45%</span>
                </div>
                <div class="w-full bg-gray-200 rounded-full h-2.5 dark:bg-gray-700">
                  <div class="bg-blue-600 h-2.5 rounded-full" style="width: 45%"></div>
                </div>
              </div>
              
              <div>
                <div class="flex justify-between mb-1">
                  <span class="text-sm font-medium text-green-700 dark:text-white">Success</span>
                  <span class="text-sm font-medium text-green-700 dark:text-white">70%</span>
                </div>
                <div class="w-full bg-gray-200 rounded-full h-2.5 dark:bg-gray-700">
                  <div class="bg-green-600 h-2.5 rounded-full" style="width: 70%"></div>
                </div>
              </div>
              
              <div>
                <div class="flex justify-between mb-1">
                  <span class="text-sm font-medium text-red-700 dark:text-white">Error</span>
                  <span class="text-sm font-medium text-red-700 dark:text-white">30%</span>
                </div>
                <div class="w-full bg-gray-200 rounded-full h-2.5 dark:bg-gray-700">
                  <div class="bg-red-600 h-2.5 rounded-full" style="width: 30%"></div>
                </div>
              </div>
            </div>
          </div>

          <div>
            <h3 class="text-lg font-medium text-gray-900 dark:text-white mb-3">Spinners</h3>
            <div class="flex gap-4 items-center">
              <Spinner size="4" />
              <Spinner size="6" color="blue" />
              <Spinner size="8" color="green" />
              <Spinner size="10" color="red" />
            </div>
          </div>
        </div>
      </Card>

      <Card class="p-6 bg-white dark:bg-gray-800 border border-gray-200 dark:border-gray-700 rounded-lg shadow-sm">
        <h2 class="text-xl font-semibold text-gray-900 dark:text-white mb-4">Avatars & Interactive</h2>
        <p class="text-gray-600 dark:text-gray-400 mb-6">User representations and interactive elements</p>

        <div class="space-y-6">
          <div>
            <h3 class="text-lg font-medium text-gray-900 dark:text-white mb-3">Avatars</h3>
            <div class="flex gap-4 items-center">
              <Avatar />
              <Avatar src="https://flowbite.com/docs/images/people/profile-picture-1.jpg" />
              <Avatar src="https://flowbite.com/docs/images/people/profile-picture-2.jpg" size="lg" />
              <Avatar size="xl" />
            </div>
          </div>

          <div>
            <h3 class="text-lg font-medium text-gray-900 dark:text-white mb-3">Modal Demo</h3>
            <Button on:click={() => modalOpen = true}>Open Modal</Button>

            <Modal bind:open={modalOpen} title="Example Modal">
              <p class="text-base leading-relaxed text-gray-500 dark:text-gray-400">
                This is a modal dialog built with Flowbite Svelte. It includes proper focus management 
                and keyboard navigation support for accessibility.
              </p>
              <div slot="footer" class="flex space-x-2">
                <Button on:click={() => modalOpen = false}>Close</Button>
                <Button color="alternative" on:click={() => modalOpen = false}>Cancel</Button>
              </div>
            </Modal>
          </div>
        </div>
      </Card>
    </div>

    <!-- Feature Summary Cards -->
    <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
      <Card class="p-6 bg-white dark:bg-gray-800 border border-gray-200 dark:border-gray-700 rounded-lg shadow-sm hover:shadow-md transition-shadow">
        <h3 class="text-xl font-semibold text-gray-900 dark:text-white mb-3">⚡ Fast Development</h3>
        <p class="text-gray-600 dark:text-gray-300 mb-4">
          Components that work seamlessly with Svelte 5 and modern development practices.
        </p>
        <Badge color="blue">Performance</Badge>
      </Card>

      <Card class="p-6 bg-white dark:bg-gray-800 border border-gray-200 dark:border-gray-700 rounded-lg shadow-sm hover:shadow-md transition-shadow">
        <h3 class="text-xl font-semibold text-gray-900 dark:text-white mb-3">🎨 Modern Styling</h3>
        <p class="text-gray-600 dark:text-gray-300 mb-4">
          Beautiful components that adapt seamlessly to both light and dark themes.
        </p>
        <Badge color="green">Design</Badge>
      </Card>

      <Card class="p-6 bg-white dark:bg-gray-800 border border-gray-200 dark:border-gray-700 rounded-lg shadow-sm hover:shadow-md transition-shadow">
        <h3 class="text-xl font-semibold text-gray-900 dark:text-white mb-3">🔧 Reliable</h3>
        <p class="text-gray-600 dark:text-gray-300 mb-4">
          All components work together harmoniously without compatibility issues.
        </p>
        <Badge color="purple">Stable</Badge>
      </Card>
    </div>
  </div>

  <!-- Footer Note -->
  <div class="mt-12 text-center">
    <p class="text-gray-600 dark:text-gray-400">
      All components are fully responsive and work seamlessly with Svelte 5 and Tailwind CSS v4. 
      This page demonstrates components implemented according to official Flowbite-Svelte documentation.
    </p>
  </div>
</div>