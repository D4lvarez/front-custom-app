<script lang="ts">
	import { NavbarLinks } from "$lib/config/navbar.config";
    import NavItem from "./NavItem.svelte";

    let isMenuOpen: boolean = false;

    const showMenu = () => {
        isMenuOpen = !isMenuOpen
    }

</script>

<nav class="flex items-center justify-between flex-wrap p-6 fixed w-full z-10 top-0 border-b-2">
    <div class="flex items-center flex-shrink-0 text-black mr-6">
        <a href="/" class="font-semibold text-xl tracking-tight">Brand</a>
    </div>
    <div class="block lg:hidden">
        <button on:click={showMenu} class="flex items-center px-3 py-2 border rounded text-black border-black hover:text-gray-700 hover:border-gray-700">
            <svg class="fill-current h-3 w-3" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"><title>Menu</title><path d="M0 3h20v2H0V3zm0 6h20v2H0V9zm0 6h20v2H0v15z"/></svg>
        </button>
    </div>
    <div class={`${isMenuOpen ? 'block': 'hidden'} w-full flex-grow lg:flex lg:items-center lg:w-auto lg:mt-0`}>
        <div class="text-sm lg:flex-grow">
            {#each NavbarLinks as navItem}
                <NavItem props={navItem}  />
            {/each}
        </div>
    </div>
</nav>