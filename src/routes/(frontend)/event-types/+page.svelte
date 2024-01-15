<script lang="ts">
	import type { PageData } from './$types';
	import { Button } from '$lib/components/ui/button';
	import { Plus, Mix } from 'radix-icons-svelte';
	import * as Dialog from '$lib/components/ui/dialog';
	import { Input } from '$lib/components/ui/input';
	import { Label } from '$lib/components/ui/label';
	import Textarea from '$lib/components/ui/textarea/textarea.svelte';

	export let data: PageData;
</script>

<div class="space-between flex items-center">
	<div class="flex items-center justify-between md:mb-6 md:mt-0 lg:mb-8 mb-0">
		<div class="space-y-1">
			<h2 class="text-2xl font-semibold tracking-tight">Event Types</h2>
			<p class="text-sm text-muted-foreground">
				Create events to share for people to book on your calendar.
			</p>
		</div>
	</div>
	<div class="ml-auto mr-4">
		<Button>
			<Plus class="mr-2 h-4 w-4" />
			New
		</Button>
	</div>
</div>

<div class="flex h-[450px] shrink-0 items-center justify-center rounded-md border border-dashed">
	<div class="mx-auto flex max-w-[420px] flex-col items-center justify-center text-center">
		<Mix class="h-16 w-16" />

		<h3 class="mt-4 text-lg font-semibold">Create your first event type</h3>
		<p class="mb-4 mt-2 text-sm text-muted-foreground">
			Event types enable you to share links that show available times on your calendar and allow
			people to make bookings with you.
		</p>
		<Dialog.Root>
			<Dialog.Trigger asChild let:builder>
				<Button size="sm" builders={[builder]} class="relative">Create</Button>
			</Dialog.Trigger>
			<Dialog.Content>
				<Dialog.Header>
					<Dialog.Title>Add a new event type</Dialog.Title>
					<Dialog.Description
						>Create a new event type for people to book times with.</Dialog.Description
					>
				</Dialog.Header>
				<div class="grid gap-4 py-4">
					<div class="grid gap-2">
						<Label for="title">Title</Label>
						<Input id="title" placeholder="Quick Chat" />
					</div>
					<div class="grid gap-2">
						<Label for="url">URL: http://localhost:3000</Label>
						<div class="mt-1 flex rounded-md shadow-sm">
							<span
								class="inline-flex items-center rounded-l-md border border-r-0 border-input bg-muted px-3 sm:text-sm"
								>/somogyi/</span
							>
							<Input class="rounded-l-none" id="url" />
						</div>
					</div>

					<div class="grid gap-2">
						<Label for="caption">Caption</Label>
						<Textarea id="caption" placeholder="A quick video meeting." />
					</div>

					<div class="grid gap-2">
						<Label for="url">Duration</Label>
						<div class="mt-1 flex rounded-md shadow-sm">
							<Input
								type="number"
								placeholder="15"
								class="rounded-r-none"
								required
								min="10"
								name="length"
							/>
							<span
								class="inline-flex items-center rounded-r-md border border-l-0 border-input bg-muted px-3 sm:text-sm"
							>
								Minutes</span
							>
						</div>
					</div>
				</div>
				<Dialog.Footer>
					<Button variant="ghost">Close</Button>
					<Button>Continue</Button>
				</Dialog.Footer>
			</Dialog.Content>
		</Dialog.Root>
	</div>
</div>
