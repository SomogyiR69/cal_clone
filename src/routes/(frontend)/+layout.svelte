<script lang="ts">
	import type { LayoutData } from './$types';
	import Sidebar from '$lib/components/layout/SideBar.svelte';
	export let data: LayoutData;
</script>

<div class="hidden md:block">
	<div class="border-t">
		<div class="bg-background">
			<div class="grid lg:grid-cols-5">
				<Sidebar />
				<div class="col-span-3 lg:col-span-4 lg:border-l">
					<div class="max-w-full px-2 py-4 lg:px-6">
						<slot />
					</div>
				</div>
			</div>
		</div>
	</div>
</div>
