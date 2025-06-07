<script>
  import { page } from '$app/stores';
  import { Button, Navbar, NavBrand, NavLi, NavUl, NavHamburger } from 'flowbite-svelte';
  import { toggleDarkMode } from '$lib/utils';
</script>

<Navbar let:hidden let:toggle>
  <NavBrand href="/">
    <span class="self-center whitespace-nowrap text-xl font-semibold text-gray-900 dark:text-white">
      SvelteKit Demo
    </span>
  </NavBrand>

  <div class="flex items-center gap-3 md:order-2">
    <!-- Dark Mode Toggle -->
    <Button on:click={toggleDarkMode} color="alternative" size="sm" class="gap-1">
      <span class="dark:hidden">🌙</span>
      <span class="hidden dark:inline">☀️</span>
    </Button>

    <!-- Mobile Menu Toggle -->
    <NavHamburger on:click={toggle} />
  </div>

  <NavUl {hidden}>
    <NavLi href="/" active={$page.url.pathname === '/'}>Home</NavLi>
    <NavLi href="/components" active={$page.url.pathname === '/components'}>Components</NavLi>
    <NavLi href="/themes" active={$page.url.pathname === '/themes'}>Themes</NavLi>
  </NavUl>
</Navbar>