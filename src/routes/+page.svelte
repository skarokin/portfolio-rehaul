<script>
    import sean from '$lib/assets/IMG_3320.jpg';
    
    import * as Avatar from '$lib/components/ui/avatar/index.js';
</script>

<div class="container flex flex-col items-start gap-2">
    <Avatar.Root class="size-48 rounded-md border-2 border-border">
        <Avatar.Image src={sean} alt="sean" />
        <Avatar.Fallback>sk</Avatar.Fallback>
    </Avatar.Root>
    
    <h1 class="text-left font-bold text-2xl sm:text-4xl w-full sm:w-3/4 mt-8">
        Hi! I'm Sean (Taemin/태민) Kim. I'm a software engineer with a passion for NLP.
    </h1>
    <div class="flex flex-col gap-1">
        <h3 class="font-semibold text-sm sm:text-base text-muted-foreground">
            CS @ Rutgers University-New Brunswick (2026)
        </h3>
        <h3 class="font-semibold text-sm sm:text-base text-muted-foreground">
            Incoming SWE Intern @ ... (2025)
        </h3>
        <h3 class="font-semibold text-sm sm:text-base text-muted-foreground">
            SWE Intern @ ACL Agency LLC (2024)
        </h3>
    </div>
</div>