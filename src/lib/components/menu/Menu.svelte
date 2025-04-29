<script>
    import { resetMode, setMode } from 'mode-watcher';

    import * as DropdownMenu from '$lib/components/ui/dropdown-menu';
    import { buttonVariants } from "$lib/components/ui/button/index.js";
    import GitHub from '$lib/assets/github.svelte';
    import Gmail from '$lib/assets/gmail.svelte';
    import LinkedIn from '$lib/assets/linkedin.svelte';
</script>

<DropdownMenu.Root>
    <DropdownMenu.Trigger class={buttonVariants({ variant: "default", size:"sm" })}>
        Menu
    </DropdownMenu.Trigger>
    <DropdownMenu.Content>
        <DropdownMenu.Group>
            <DropdownMenu.GroupHeading class="text-xs">
                Theme
            </DropdownMenu.GroupHeading>
            <DropdownMenu.Separator />
            <DropdownMenu.Item class="text-xs" onclick={() => resetMode()}>System</DropdownMenu.Item>
            <DropdownMenu.Item class="text-xs" onclick={() => setMode('light')}>Light</DropdownMenu.Item>
            <DropdownMenu.Item class="text-xs" onclick={() => setMode('dark')}>Dark</DropdownMenu.Item>
        </DropdownMenu.Group>
        <DropdownMenu.Group>
            <DropdownMenu.Separator />
            <DropdownMenu.GroupHeading class="text-xs">
                Navigation
            </DropdownMenu.GroupHeading>
            <DropdownMenu.Separator />
            <DropdownMenu.Item>
                <a href="/" class="text-xs block w-full">Home</a>
            </DropdownMenu.Item>
            <DropdownMenu.Item>
                <a href="/projects" class="text-xs block w-full">Projects</a>
            </DropdownMenu.Item>
            <DropdownMenu.Item>
                <a href="/resume" class="text-xs block w-full">Resume</a>
            </DropdownMenu.Item>
            <DropdownMenu.Item>
                <a href="/contacts" class="text-xs block w-full">Contacts</a>
            </DropdownMenu.Item>
        </DropdownMenu.Group>
        <DropdownMenu.Group>
            <DropdownMenu.Separator />
            <DropdownMenu.GroupHeading class="text-xs">
                Links
            </DropdownMenu.GroupHeading>
            <DropdownMenu.Separator />
            <DropdownMenu.Item>
                <GitHub />
                <a
                    class="ml-2 text-xs"
                    href="https://www.github.com/skarokin/"
                    target="_blank"
                >
                    GitHub
                </a>
            </DropdownMenu.Item>
            <DropdownMenu.Item>
                <Gmail />
                <a
                    class="ml-2 text-xs"
                    href="mailto:taemin.kim0327@gmail.com"
                    target="_blank"
                    >Email
                </a>
            </DropdownMenu.Item>
            <DropdownMenu.Item>
                <LinkedIn />
                <a
                    class="ml-2 text-xs"
                    href="https://www.linkedin.com/in/kimtaemin/"
                    target="_blank"
                >
                    LinkedIn
                </a>
            </DropdownMenu.Item>
        </DropdownMenu.Group>
    </DropdownMenu.Content>
</DropdownMenu.Root>