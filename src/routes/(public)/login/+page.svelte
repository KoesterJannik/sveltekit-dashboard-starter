<script lang="ts">
	import { Button } from '$lib/components/ui/button';
	import { Input } from '$lib/components/ui/input';
	import { Label } from '$lib/components/ui/label';
	import { ExclamationTriangle } from 'radix-icons-svelte';
	import * as Alert from '$lib/components/ui/alert';
	import type { PageData } from './$types';

	export let data: PageData;
	export let form;
</script>

<div
	class="mx-auto flex h-screen max-w-[350px] flex-col items-center justify-center space-y-6 overflow-hidden"
>
	<div class="space-y-2 text-center">
		<h1 class="text-3xl font-bold">Sign In</h1>
		<p class="text-gray-500 dark:text-gray-400">Enter your information to sign in</p>
	</div>
	<div>
		<form class="space-y-4" method="post" action="?/loginUser">
			<div class="grid w-full max-w-sm items-center gap-1.5">
				<Label for="email">Email</Label>
				<Input type="email" name="email" placeholder="email" required />
			</div>
			<div class="grid w-full max-w-sm items-center gap-1.5">
				<Label for="email">Email</Label>
				<Input type="password" placeholder="Password" name="password" required />
			</div>

			<Button
				class="inline-flex h-10 w-full items-center justify-center whitespace-nowrap rounded-md bg-primary px-4 py-2 text-sm font-medium text-primary-foreground ring-offset-background transition-colors hover:bg-primary/90 focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-ring focus-visible:ring-offset-2 disabled:pointer-events-none disabled:opacity-50"
				type="submit"
			>
				Sign In
			</Button>
		</form>
		{#if form?.errorMessage}<Alert.Root variant="destructive" class="mt-2">
				<ExclamationTriangle class="h-4 w-4" />
				<Alert.Title>Error</Alert.Title>
				<Alert.Description>{form?.errorMessage}</Alert.Description>
			</Alert.Root>{/if}

		<div class="mb-0 mt-3">
			<a href="/register" class="text-color">Need an account?</a>
		</div>
	</div>
</div>
