<script lang="ts">
	import { cn } from '$lib/utils';
	import { Button, buttonVariants } from '$lib/components/ui/button';
	import * as DropdownMenu from '$lib/components/ui/dropdown-menu';
	import * as Dialog from '$lib/components/ui/dialog';
	import { Input } from '$lib/components/ui/input';
	import { Label } from '$lib/components/ui/label';

	import {
		Avatar,
		BarChart,
		Calendar,
		Clock,
		File,
		Grid,
		LightningBolt,
		MagnifyingGlass,
		Mix,
		Person
	} from 'radix-icons-svelte';
</script>

<aside class="pb-12 h-screen">
	<div class="space-y-4 py-4">
		<div class="px-3 py-2">
			<div class="flex mb-4">
				<DropdownMenu.Root>
					<DropdownMenu.Trigger asChild let:builder>
						<Button builders={[builder]} variant="ghost">
							<Avatar class="mr-2 h-6 w-6" />
							Somogyi Roland</Button
						>
					</DropdownMenu.Trigger>
					<DropdownMenu.Content class="w-56">
						<DropdownMenu.Label>My Account</DropdownMenu.Label>
						<DropdownMenu.Separator />
						<DropdownMenu.Group>
							<DropdownMenu.Item>
								Profile
								<DropdownMenu.Shortcut>⇧⌘P</DropdownMenu.Shortcut>
							</DropdownMenu.Item>
							<DropdownMenu.Item>
								Billing
								<DropdownMenu.Shortcut>⌘B</DropdownMenu.Shortcut>
							</DropdownMenu.Item>
							<DropdownMenu.Item>
								Settings
								<DropdownMenu.Shortcut>⌘S</DropdownMenu.Shortcut>
							</DropdownMenu.Item>
							<DropdownMenu.Item>
								Keyboard shortcuts
								<DropdownMenu.Shortcut>⌘K</DropdownMenu.Shortcut>
							</DropdownMenu.Item>
						</DropdownMenu.Group>
						<DropdownMenu.Separator />
						<DropdownMenu.Group>
							<DropdownMenu.Item>Team</DropdownMenu.Item>
							<DropdownMenu.Sub>
								<DropdownMenu.SubTrigger>Invite users</DropdownMenu.SubTrigger>
								<DropdownMenu.SubContent>
									<DropdownMenu.Item>Email</DropdownMenu.Item>
									<DropdownMenu.Item>Message</DropdownMenu.Item>
									<DropdownMenu.Separator />
									<DropdownMenu.Item>More...</DropdownMenu.Item>
								</DropdownMenu.SubContent>
							</DropdownMenu.Sub>
							<DropdownMenu.Item>
								New Team
								<DropdownMenu.Shortcut>⌘+T</DropdownMenu.Shortcut>
							</DropdownMenu.Item>
						</DropdownMenu.Group>
						<DropdownMenu.Separator />
						<DropdownMenu.Item>GitHub</DropdownMenu.Item>
						<DropdownMenu.Item>Support</DropdownMenu.Item>
						<DropdownMenu.Item>API</DropdownMenu.Item>
						<DropdownMenu.Separator />
						<DropdownMenu.Item>
							Log out
							<DropdownMenu.Shortcut>⇧⌘Q</DropdownMenu.Shortcut>
						</DropdownMenu.Item>
					</DropdownMenu.Content>
				</DropdownMenu.Root>

				<Dialog.Root>
					<Dialog.Trigger class={buttonVariants({ variant: 'ghost' })}
						><MagnifyingGlass class="h-4 w-4" /></Dialog.Trigger
					>
					<Dialog.Content class="sm:max-w-[425px]">
						<Dialog.Header>
							<Dialog.Title>Edit profile</Dialog.Title>
							<Dialog.Description>
								Make changes to your profile here. Click save when you're done.
							</Dialog.Description>
						</Dialog.Header>
						<div class="grid gap-4 py-4">
							<div class="grid grid-cols-4 items-center gap-4">
								<Label for="name" class="text-right">Name</Label>
								<Input id="name" value="Pedro Duarte" class="col-span-3" />
							</div>
							<div class="grid grid-cols-4 items-center gap-4">
								<Label for="username" class="text-right">Username</Label>
								<Input id="username" value="@peduarte" class="col-span-3" />
							</div>
						</div>
						<Dialog.Footer>
							<Button type="submit">Save changes</Button>
						</Dialog.Footer>
					</Dialog.Content>
				</Dialog.Root>
			</div>
			<div class="space-y-0.5">
				<Button variant="secondary" class="w-full justify-start">
					<Mix class="mr-2 h-4 w-4" />
					Event Types
				</Button>
				<Button variant="ghost" class="w-full justify-start">
					<Calendar class="mr-2 h-4 w-4" />
					Bookings
				</Button>
				<Button variant="ghost" class="w-full justify-start">
					<Clock class="mr-2 h-4 w-4" />
					Availability
				</Button>
				<Button variant="ghost" class="w-full justify-start">
					<Person class="mr-2 h-4 w-4" />
					Teams
				</Button>
				<Button variant="ghost" class="w-full justify-start">
					<Grid class="mr-2 h-4 w-4" />
					Apps
				</Button>
				<Button variant="ghost" class="w-full justify-start">
					<File class="mr-2 h-4 w-4" />
					Routing Forms
				</Button>
				<Button variant="ghost" class="w-full justify-start">
					<LightningBolt class="mr-2 h-4 w-4" />
					Workflows
				</Button>
				<Button variant="ghost" class="w-full justify-start">
					<BarChart class="mr-2 h-4 w-4" />
					Inshights
				</Button>
			</div>
		</div>
	</div>
</aside>
