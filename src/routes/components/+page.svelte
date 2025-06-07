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
    Progress,
    Avatar,
    Breadcrumb,
    BreadcrumbItem
  } from 'flowbite-svelte';
  import { InfoCircleSolid, ExclamationTriangleSolid, CheckCircleSolid } from 'flowbite-svelte-icons';

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
    <!-- Buttons -->
    <Card class="max-w-none">
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
      <Card class="max-w-none">
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

      <Card class="max-w-none">
        <h2 class="text-xl font-semibold text-gray-900 dark:text-white mb-4">Alerts</h2>
        <p class="text-gray-600 dark:text-gray-400 mb-6">User feedback and notification messages</p>

        <div class="space-y-4">
          <Alert color="blue">
            <InfoCircleSolid slot="icon" class="w-4 h-4" />
            <span class="font-medium">Info alert!</span> Change a few things up and try submitting again.
          </Alert>

          <Alert color="green">
            <CheckCircleSolid slot="icon" class="w-4 h-4" />
            <span class="font-medium">Success alert!</span> Your changes have been saved successfully.
          </Alert>

          <Alert color="yellow">
            <ExclamationTriangleSolid slot="icon" class="w-4 h-4" />
            <span class="font-medium">Warning alert!</span> Please review your information before proceeding.
          </Alert>

          <Alert color="red">
            <ExclamationTriangleSolid slot="icon" class="w-4 h-4" />
            <span class="font-medium">Error alert!</span> Something went wrong. Please try again.
          </Alert>
        </div>
      </Card>
    </div>

    <!-- Form Components -->
    <Card class="max-w-none">
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

    <!-- Progress & Loading -->
    <div class="grid grid-cols-1 lg:grid-cols-2 gap-8">
      <Card class="max-w-none">
        <h2 class="text-xl font-semibold text-gray-900 dark:text-white mb-4">Progress Indicators</h2>
        <p class="text-gray-600 dark:text-gray-400 mb-6">Visual feedback for loading states and progress</p>

        <div class="space-y-6">
          <div>
            <h3 class="text-lg font-medium text-gray-900 dark:text-white mb-3">Progress Bars</h3>
            <div class="space-y-4">
              <Progress progress="45" />
              <Progress progress="70" color="green" />
              <Progress progress="30" color="red" />
              <Progress progress="85" color="yellow" />
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

      <Card class="max-w-none">
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
  </div>
</div>