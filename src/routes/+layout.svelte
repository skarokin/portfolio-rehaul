<script lang="ts">
    import '../app.css';
    import { page } from '$app/state';

    import { ModeWatcher } from 'mode-watcher';
    import Menu from '$lib/components/menu/Menu.svelte';
    
    let { children } = $props();
</script>

<ModeWatcher />
<div class="h-full flex flex-col justify-stretch w-full">
    <header class="sticky top-0 z-50 w-full border-b bg-background/95 backdrop-blur supports-[backdrop-filter]:bg-background/60">
        <div class="container flex h-14 items-center justify-between">
            <div class="flex items-center gap-12">
                <a href="/" class="hidden sm:inline-block font-bold">
                    [skarokin]
                </a>
                <nav class="flex items-center gap-6 text-sm">
                    <a
                        class={`hover:text-foreground/80 transition-colors ${page.url.pathname === '/projects' ? 'text-foreground' : 'text-foreground/60'}`}
                        href="/projects"
                    >
                        Projects
                    </a>
                    <a 
                        class={`hover:text-foreground/80 transition-colors ${page.url.pathname === '/resume' ? 'text-foreground' : 'text-foreground/60'}`}
                        href="/resume"
                    >
                        Resume
                    </a>
                    <a
                        class={`hover:text-foreground/80 transition-colors ${page.url.pathname === '/contacts' ? 'text-foreground' : 'text-foreground/60'}`}
                        href="/contacts"
                    >
                        Contacts
                    </a>
                </nav>
            </div>
            <Menu />
        </div>
    </header>
    <main class="w-full bg-background overflow-auto py-16 px-0 sm:px-24">
        {@render children()}
    </main>
</div>