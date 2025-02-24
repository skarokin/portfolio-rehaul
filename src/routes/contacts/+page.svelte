<script lang="ts">
    import { Button } from "$lib/components/ui/button";
    import * as Table from "$lib/components/ui/table/index.js";
    import { Badge } from "$lib/components/ui/badge";

    const contacts = [
        {
            method: "Email",
            value: "taemin.kim0327@gmail.com",
            href: "mailto:taemin.kim0327@gmail.com",
            preferability: "High"
        },
        {
            method: "LinkedIn",
            value: "sean-kim-959174238",
            href: "https://www.linkedin.com/in/sean-kim-959174238/",
            preferability: "Med"
        },
        {
            method: "Phone",
            value: "+1 (201) 937-7441",
            href: "tel:+12019377441",
            preferability: "Low"
        },
        {
            method: "GitHub",
            value: "skarokin",
            href: "https://www.github.com/skarokin",
            preferability: "N/A"
        },
    ]
</script>

<div class="container flex flex-col items-start gap-2">
    <h1 class="text-4xl font-bold">Contacts</h1>
    <p class="text-sm text-muted-foreground">Interested in working together? Feel free to reach out!</p>
    <Table.Root class="text-xs sm:text-sm mt-8">
        <Table.Header>
            <Table.Row>
                <Table.Head class="w-[150px]">Method</Table.Head>
                <Table.Head class="w-[150px]">Value</Table.Head>
                <Table.Head class="w-[150px]">Preferability</Table.Head>
            </Table.Row>
        </Table.Header>
        <Table.Body>
            {#each contacts as contact, i (i)}
                <Table.Row>
                    <Table.Cell class="font-medium">
                        {contact.method}
                    </Table.Cell>
                    <Table.Cell>
                        <Badge variant="outline">
                            <a
                                href={contact.href}
                                target="_blank"
                                rel="noopener noreferrer"
                                class="p-0"
                            >
                                {contact.value}
                            </a>
                        </Badge>
                    </Table.Cell>
                    <Table.Cell>
                        {contact.preferability}
                    </Table.Cell>
                </Table.Row>
            {/each}
        </Table.Body>
    </Table.Root>
</div>
