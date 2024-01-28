<script>
	import { page } from '$app/stores';
	import { navLinks } from '../routes/links';
</script>

<nav class=" mt-0 w-full border bg-gray-800 p-2">
	<div class=" flex flex-wrap items-center">
		<div class="flex w-full justify-center font-extrabold text-white md:w-1/2 md:justify-start">
			<a class="text-white no-underline hover:text-white hover:no-underline" href="#">
				<span class="pl-2 text-2xl"><i class="em em-grinning"></i> BrandName</span>
			</a>
		</div>
		<div class="flex w-full content-center justify-between pt-2 md:w-1/2 md:justify-end">
			<ul class="list-reset flex flex-1 items-center justify-between md:flex-none">
				{#each navLinks as link}
					<li class="mr-3">
						<a
							class="inline-block px-4 py-2 text-white no-underline ${$page.url.pathname ==
							link.path
								? 'underline'
								: ''}"
							href={link.path}>{link.name}</a
						>
					</li>
				{/each}
			</ul>
		</div>
	</div>
</nav>
