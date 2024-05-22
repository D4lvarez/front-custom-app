<script lang="ts">
	import type { INavbarItem } from "$lib/interfaces/navbarItem.interface";

    export let props: INavbarItem;
</script>

<a href={props.link} class="block mt-4 lg:inline-block lg:mt-0 text-black hover:border-b-2 hover:text-gray-700 mr-4">
    {props.title}
</a>