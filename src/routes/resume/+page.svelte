<script lang="ts">
    import resume from "$lib/assets/SeanKimResumeFeb2025.pdf";
    import { Button } from "$lib/components/ui/button";
    import { Download } from "lucide-svelte";
</script>

<div class="container flex flex-col items-start gap-2">
    <h1 class="text-4xl font-bold">Resume</h1>
    <p class="text-sm text-muted-foreground">Last updated: February 23, 2025</p>

    <Button
        href={resume}
        target="_blank"
        rel="noopener noreferrer"
        class="mt-8"
    >
        <Download class="mr-2" />
        Download Resume
    </Button>
</div>
