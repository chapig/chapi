<script lang="ts">
    import { Button } from "$lib/components/ui/button";
    import * as Sheet from "$lib/components/ui/sheet";
    import { Moon, Sun } from "lucide-svelte";
    import { toggleMode } from "mode-watcher";
    import Menu from "lucide-svelte/icons/menu";
	import { Linkedin, Github, Mail } from "lucide-svelte";
</script>
<header class="sticky top-0 z-40 flex h-16 items-center justify-between px-4 md:px-6">
	<nav class="hidden md:flex items-center gap-6 text-sm font-medium">
		<a href="/" class="text-lg font-semibold">chapi.dev</a>
		<a href="/resume">Resume</a>
		<a href="/contact">Contact</a>
	</nav>

	<div class="flex items-center gap-4"> 
		<Button on:click={toggleMode} variant="outline" size="icon">
			<Sun
				class="h-[1.2rem] w-[1.2rem] rotate-0 scale-100 transition-all dark:-rotate-90 dark:scale-0"
			/>
			<Moon
				class="absolute h-[1.2rem] w-[1.2rem] rotate-90 scale-0 transition-all dark:rotate-0 dark:scale-100"
			/>
			<span class="sr-only">Toggle theme</span>
		</Button>
	</div>

	<Sheet.Root>
		<Sheet.Trigger asChild let:builder>
			<Button variant="ghost" size="icon" class="md:hidden" builders={[builder]}>
				<Menu class="h-5 w-5" />
			</Button>
		</Sheet.Trigger>
		<Sheet.Content side="right" class="w-60"> 
			<nav class="grid gap-4 p-4 text-sm font-medium">
				<a href="/" class="text-lg font-semibold">chapi.dev</a>
				<a href="/resume">Resume</a>
				<a href="/contact">Contact</a>
			</nav>
			<!--Social Media Links and Footer-->

			<div class="flex justify-center gap-4 p-4 border-t w-60">
				<a href="https://www.linkedin.com/in/chaparroluis/" target="_blank" rel="noopener noreferrer">
					<Linkedin class="w-5 h-5" />
				</a>
				<a href="https://www.github.com/chapig" target="_blank" rel="noopener noreferrer">
					<Github class="w-5 h-5" />
				</a>
				<a href="mailto:luis@chapi.dev">
					<Mail class="w-5 h-5" />
				</a>
			</div>

		</Sheet.Content>
	</Sheet.Root>
</header>