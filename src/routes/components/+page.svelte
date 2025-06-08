<!-- src/routes/components/+page.svelte -->

<script>
  import { Button, Card, Badge, Input, Label, Alert } from 'flowbite-svelte';

  let textInput = '';
  let emailInput = '';
  let checkboxValue = false;
  let radioValue = 'option1';
  let showAlert = true;
</script>

<svelte:head>
  <title>Components Demo - Flowbite Svelte</title>
</svelte:head>

<div class="min-h-screen bg-white dark:bg-gray-900 transition-colors duration-200">
  <div class="container mx-auto px-4 py-8">
    
    <!-- Breadcrumb (Simple) -->
    <nav class="flex mb-6" aria-label="Breadcrumb">
      <ol class="inline-flex items-center space-x-1 md:space-x-3">
        <li class="inline-flex items-center">
          <a href="/" class="inline-flex items-center text-sm font-medium text-gray-700 hover:text-blue-600 dark:text-gray-400 dark:hover:text-white">
            <svg class="w-3 h-3 me-2.5" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="currentColor" viewBox="0 0 20 20">
              <path d="m19.707 9.293-2-2-7-7a1 1 0 0 0-1.414 0l-7 7-2 2a1 1 0 0 0 1.414 1.414L2 10.414V18a2 2 0 0 0 2 2h3a1 1 0 0 0 1-1v-4a1 1 0 0 1 1-1h2a1 1 0 0 1 1 1v4a1 1 0 0 0 1 1h3a2 2 0 0 0 2-2v-7.586l.293.293a1 1 0 0 0 1.414-1.414Z"/>
            </svg>
            Home
          </a>
        </li>
        <li>
          <div class="flex items-center">
            <svg class="rtl:rotate-180 w-3 h-3 text-gray-400 mx-1" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 6 10">
              <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="m1 9 4-4-4-4"/>
            </svg>
            <span class="ms-1 text-sm font-medium text-gray-500 md:ms-2 dark:text-gray-400">Components</span>
          </div>
        </li>
      </ol>
    </nav>

    <h1 class="text-3xl font-bold text-gray-900 dark:text-white mb-8">
      Flowbite Svelte Components Demo
    </h1>

    <div class="grid gap-8">
      <!-- Buttons -->
      <Card class="max-w-none bg-white dark:bg-gray-800 border border-gray-200 dark:border-gray-700">
        <h2 class="text-xl font-semibold text-gray-900 dark:text-white mb-4">Buttons</h2>
        <p class="text-gray-600 dark:text-gray-300 mb-6">Various button styles and variants with working hover effects</p>

        <div class="space-y-4">
          <!-- Primary Buttons -->
          <div>
            <h3 class="text-lg font-medium text-gray-900 dark:text-white mb-3">Primary Buttons</h3>
            <div class="flex flex-wrap gap-3">
              <Button class="text-white bg-blue-700 hover:bg-blue-800 focus:ring-4 focus:ring-blue-300 font-medium rounded-lg text-sm px-5 py-2.5 dark:bg-blue-600 dark:hover:bg-blue-700 focus:outline-none dark:focus:ring-blue-800">
                Default
              </Button>
              <Button color="green" class="text-white bg-green-700 hover:bg-green-800 focus:ring-4 focus:ring-green-300 font-medium rounded-lg text-sm px-5 py-2.5 dark:bg-green-600 dark:hover:bg-green-700 focus:outline-none dark:focus:ring-green-800">
                Green
              </Button>
              <Button color="red" class="text-white bg-red-700 hover:bg-red-800 focus:ring-4 focus:ring-red-300 font-medium rounded-lg text-sm px-5 py-2.5 dark:bg-red-600 dark:hover:bg-red-700 focus:outline-none dark:focus:ring-red-800">
                Red
              </Button>
              <Button color="yellow" class="text-white bg-yellow-400 hover:bg-yellow-500 focus:ring-4 focus:ring-yellow-300 font-medium rounded-lg text-sm px-5 py-2.5 dark:focus:ring-yellow-900">
                Yellow
              </Button>
            </div>
          </div>

          <!-- Button Variants -->
          <div>
            <h3 class="text-lg font-medium text-gray-900 dark:text-white mb-3">Button Variants</h3>
            <div class="flex flex-wrap gap-3">
              <Button color="alternative" class="py-2.5 px-5 text-sm font-medium text-gray-900 focus:outline-none bg-white rounded-lg border border-gray-200 hover:bg-gray-100 hover:text-blue-700 focus:z-10 focus:ring-4 focus:ring-gray-200 dark:focus:ring-gray-700 dark:bg-gray-800 dark:text-gray-400 dark:border-gray-600 dark:hover:text-white dark:hover:bg-gray-700">
                Alternative
              </Button>
              <Button outline class="text-blue-700 hover:text-white border border-blue-700 hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300 font-medium rounded-lg text-sm px-5 py-2.5 text-center dark:border-blue-500 dark:text-blue-500 dark:hover:text-white dark:hover:bg-blue-500 dark:focus:ring-blue-800">
                Outline
              </Button>
            </div>
          </div>
        </div>
      </Card>

      <!-- Form Components -->
      <Card class="max-w-none bg-white dark:bg-gray-800 border border-gray-200 dark:border-gray-700">
        <h2 class="text-xl font-semibold text-gray-900 dark:text-white mb-4">Form Components</h2>
        <p class="text-gray-600 dark:text-gray-300 mb-6">Interactive form controls with proper styling</p>

        <div class="grid grid-cols-1 lg:grid-cols-2 gap-8">
          <div class="space-y-6">
            <!-- Text Inputs -->
            <div>
              <Label for="text-input" class="mb-2 text-gray-900 dark:text-white">Text Input</Label>
              <Input 
                id="text-input" 
                bind:value={textInput}
                placeholder="Enter text here" 
                class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
              />
              {#if textInput}
                <p class="mt-2 text-sm text-gray-600 dark:text-gray-400">You typed: {textInput}</p>
              {/if}
            </div>

            <div>
              <Label for="email-input" class="mb-2 text-gray-900 dark:text-white">Email Input</Label>
              <Input 
                id="email-input" 
                type="email" 
                bind:value={emailInput}
                placeholder="your.email@example.com" 
                class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
              />
            </div>

            <!-- Simple Checkbox -->
            <div class="flex items-start">
              <div class="flex items-center h-5">
                <input 
                  id="terms" 
                  bind:checked={checkboxValue}
                  type="checkbox" 
                  class="w-4 h-4 border border-gray-300 rounded bg-gray-50 focus:ring-3 focus:ring-blue-300 dark:bg-gray-700 dark:border-gray-600 dark:focus:ring-blue-600 dark:ring-offset-gray-800 dark:focus:ring-offset-gray-800"
                />
              </div>
              <label for="terms" class="ms-2 text-sm font-medium text-gray-900 dark:text-gray-300">
                I agree to the terms and conditions
              </label>
            </div>

            <!-- Simple Radio Buttons -->
            <div>
              <h3 class="text-lg font-medium text-gray-900 dark:text-white mb-3">Radio Buttons</h3>
              <div class="space-y-3">
                <div class="flex items-center">
                  <input 
                    id="option1" 
                    type="radio" 
                    bind:group={radioValue} 
                    value="option1" 
                    class="w-4 h-4 text-blue-600 bg-gray-100 border-gray-300 focus:ring-blue-500 dark:focus:ring-blue-600 dark:ring-offset-gray-800 focus:ring-2 dark:bg-gray-700 dark:border-gray-600"
                  />
                  <label for="option1" class="ms-2 text-sm font-medium text-gray-900 dark:text-gray-300">Option 1</label>
                </div>
                <div class="flex items-center">
                  <input 
                    id="option2" 
                    type="radio" 
                    bind:group={radioValue} 
                    value="option2" 
                    class="w-4 h-4 text-blue-600 bg-gray-100 border-gray-300 focus:ring-blue-500 dark:focus:ring-blue-600 dark:ring-offset-gray-800 focus:ring-2 dark:bg-gray-700 dark:border-gray-600"
                  />
                  <label for="option2" class="ms-2 text-sm font-medium text-gray-900 dark:text-gray-300">Option 2</label>
                </div>
              </div>
            </div>
          </div>

          <div class="space-y-6">
            <!-- Badges -->
            <div>
              <h3 class="text-lg font-medium text-gray-900 dark:text-white mb-3">Badges</h3>
              <div class="flex flex-wrap gap-2">
                <Badge class="bg-blue-100 text-blue-800 text-xs font-medium px-2.5 py-0.5 rounded dark:bg-blue-900 dark:text-blue-300">Default</Badge>
                <Badge color="green" class="bg-green-100 text-green-800 text-xs font-medium px-2.5 py-0.5 rounded dark:bg-green-900 dark:text-green-300">Success</Badge>
                <Badge color="red" class="bg-red-100 text-red-800 text-xs font-medium px-2.5 py-0.5 rounded dark:bg-red-900 dark:text-red-300">Error</Badge>
                <Badge color="yellow" class="bg-yellow-100 text-yellow-800 text-xs font-medium px-2.5 py-0.5 rounded dark:bg-yellow-900 dark:text-yellow-300">Warning</Badge>
              </div>
            </div>

            <!-- Interactive Alert -->
            <div>
              <h3 class="text-lg font-medium text-gray-900 dark:text-white mb-3">Interactive Alert</h3>
              <Button 
                on:click={() => showAlert = !showAlert}
                class="text-white bg-purple-700 hover:bg-purple-800 focus:ring-4 focus:ring-purple-300 font-medium rounded-lg text-sm px-5 py-2.5 mb-4 dark:bg-purple-600 dark:hover:bg-purple-700 focus:outline-none dark:focus:ring-purple-800"
              >
                {showAlert ? 'Hide' : 'Show'} Alert
              </Button>
              
              {#if showAlert}
                <Alert color="blue" class="flex items-center p-4 text-blue-800 rounded-lg bg-blue-50 dark:bg-gray-800 dark:text-blue-400">
                  <svg class="flex-shrink-0 w-4 h-4" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="currentColor" viewBox="0 0 20 20">
                    <path d="M10 .5a9.5 9.5 0 1 0 9.5 9.5A9.51 9.51 0 0 0 10 .5ZM9.5 4a1.5 1.5 0 1 1 0 3 1.5 1.5 0 0 1 0-3ZM12 15H8a1 1 0 0 1 0-2h1v-3H8a1 1 0 0 1 0-2h2a1 1 0 0 1 1 1v4h1a1 1 0 0 1 0 2Z"/>
                  </svg>
                  <span class="sr-only">Info</span>
                  <div class="ms-3 text-sm font-medium">
                    This is a dynamic alert that can be toggled on and off! Current inputs: Text="{textInput}", Email="{emailInput}", Checkbox={checkboxValue}, Radio="{radioValue}"
                  </div>
                </Alert>
              {/if}
            </div>
          </div>
        </div>
      </Card>

      <!-- Cards and Layout -->
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
        <Card class="bg-white dark:bg-gray-800 border border-gray-200 dark:border-gray-700">
          <h3 class="text-xl font-semibold text-gray-900 dark:text-white mb-3">⚡ Fast Development</h3>
          <p class="text-gray-600 dark:text-gray-300 mb-4">
            Components that work seamlessly with Svelte 5 and modern development practices.
          </p>
          <Badge color="blue" class="bg-blue-100 text-blue-800 text-xs font-medium px-2.5 py-0.5 rounded dark:bg-blue-900 dark:text-blue-300">Performance</Badge>
        </Card>

        <Card class="bg-white dark:bg-gray-800 border border-gray-200 dark:border-gray-700">
          <h3 class="text-xl font-semibold text-gray-900 dark:text-white mb-3">🎨 Modern Styling</h3>
          <p class="text-gray-600 dark:text-gray-300 mb-4">
            Beautiful components that adapt seamlessly to both light and dark themes.
          </p>
          <Badge color="green" class="bg-green-100 text-green-800 text-xs font-medium px-2.5 py-0.5 rounded dark:bg-green-900 dark:text-green-300">Design</Badge>
        </Card>

        <Card class="bg-white dark:bg-gray-800 border border-gray-200 dark:border-gray-700">
          <h3 class="text-xl font-semibold text-gray-900 dark:text-white mb-3">🔧 Reliable</h3>
          <p class="text-gray-600 dark:text-gray-300 mb-4">
            All components work together harmoniously without compatibility issues.
          </p>
          <Badge color="purple" class="bg-purple-100 text-purple-800 text-xs font-medium px-2.5 py-0.5 rounded dark:bg-purple-900 dark:text-purple-300">Stable</Badge>
        </Card>
      </div>

      <!-- Footer Note -->
      <div class="mt-12 text-center">
        <p class="text-gray-600 dark:text-gray-400">
          All components are fully responsive and work seamlessly with Svelte 5 and Tailwind CSS v4.
          This page demonstrates components that are known to be compatible.
        </p>
      </div>

    </div>
  </div>
</div>