<script lang="ts">
    import * as Tabs from "$lib/components/ui/tabs/index.js";
    import * as Card from "$lib/components/ui/card/index.js";
    import * as Table from "$lib/components/ui/table/index.js";
    import { buttonVariants } from "$lib/components/ui/button";
    import { Badge } from "$lib/components/ui/badge/index.js";

    const cards = [
        {
            title: "copium.dev",
            description: "Tech internship management platform with real-time search, data analytics, and live postings.\
            Backend infrastructure scalable to millions with microservices and message queues.",
            date: "Jan 2025 - Present",
            link: "https://copium.dev",
            github: "https://github.com/copium-dev/copium",
            table: [
                {
                    tech: "SvelteKit & Vercel",
                    purpose: "Frontend Development",
                    results: "Responsive, beautiful, and accessible design with SSR and easy CI/CD."
                },
                {
                    tech: "Algolia",
                    purpose: "Search Engine",
                    results: "Real-time search and filtering on internship postings or user's tracked applications.",
                },
                {
                    tech: "Go & Firestore",
                    purpose: "REST API & Storage",
                    results: "Front-facing REST API for authentication, Algolia searching, and data analytics.",
                },
                {
                    tech: "Cloud Pub/Sub",
                    purpose: "Messaging Service",
                    results: "Decoupled and fault-tolerant Algolia indexing and BigQuery analytics with compensating transactions and retries for eventual consistency.", 
                },
                {
                    tech: "BigQuery & CQRS",
                    purpose: "Real-time Analytics",
                    results: "Personalized insights by tracking monthly trends, leveraging a denormalized schema and CQRS for fast queries."
                },
                {
                    tech: "Docker & GCP",
                    purpose: "Deployment",
                    results: "Containerized, scalable, and fault-tolerant deployment across VM instances and serverless functions.",
                },
                {
                    tech: "Python",
                    purpose: "Data Scraping",
                    results: "Scheduled tech internship posting scraping for focused and fresh data.",
                },
            ],
        },
        {
            title: "ref:note",
            description: "Student-focused note sharing platform with real-time collaboration, leveraging horizontally-scaling WebSocket servers.",
            date: "Aug 2024 - Sep 2024",
            link: "https://refnote.app",
            github: "https://www.github.com/skarokin/ref-note",
            table: [
                {
                    tech: "Next.js & Vercel",
                    purpose: "Frontend Development",
                    results: "Combination of CSR and SSR, API routes for authentication, and dynamic routing."
                },
                {
                    tech: "Go & Firestore",
                    purpose: "REST API",
                    results: "Front-facing REST API for CRUD and granular note sharing."
                },
                {
                    tech: "Node.js & WebSocket",
                    purpose: "Real-time Collaboration",
                    results: "Horizontally scalable WebSocket servers for real-time collaboration."
                },
                {
                    tech: "Redis & Redis Pub/Sub",
                    purpose: "Caching & Syncing",
                    results: "Note content caching and eventually-consistent architecture between instances with CRDTs."
                },
                {
                    tech: "GCP & Docker",
                    purpose: "Deployment",
                    results: "Containerized, scalable, and fault-tolerant deployment."
                }
            ]
        },
        {
            title: "grammaCy",
            description: "Generate dependency tree-based grammar checkers for any language, any dataset, and any domain.",
            date: "Mar 2024 - Jul 2024",
            link: "https://grammacy.com",
            github: "https://www.github.com/skarokin/grammacy",
            table: [
                {
                    tech: "Python",
                    purpose: "Augmentation Pipeline",
                    results: "Injects real-world grammar errors via inflection into datasets by analyzing dependency trees, POS tags, and morphological features."
                },
                {
                    tech: "Flask",
                    purpose: "REST API",
                    results: "Easy API development to serve our fully-featured English grammar and spell checker."
                },
                {
                    tech: "AWS & Docker & Nginx",
                    purpose: "Deployment",
                    results: "Fault-tolerant and HTTPS-secured API calls for quick, accurate, and interpretable grammar and spell checking.",
                },
                {
                    tech: "SvelteKit & Firebase",
                    purpose: "Documentation & API Reference",
                    results: "Interactive API reference, extensive integration guides, detailed documentation, and devblog.",
                }
            ]
        },
        {
            title: "pycaptcha",
            description: "CAPTCHA system that fetches Google Street View images to generate image-based tests",
            date: "Jan 2024 - Feb 2024",
            link: "",
            github: "https://www.github.com/skarokin/pycaptcha",
            table: [
                {
                    tech: "NumPy, OpenCV, Matplotlib",
                    purpose: "Image Augmentation",
                    results: "Augmentation pipeline for more robust and diverse image-based CAPTCHAs."
                },
                {
                    tech: "YOLOv4",
                    purpose: "Object Detection",
                    results: "Detect objects for grid-based object selection CAPTCHAs."
                },
                {
                    tech: "Pandas",
                    purpose: "Data Preprocessing",
                    results: "Process and filter images before test generation for higher quality CAPTCHAs."
                }
            ]
        },
        {
            title: "ref:type",
            description: "Competitive typing platform with real-time leaderboards",
            date: "Nov 2023 - Jan 2024",
            link: "https://steam-link-409216.web.app/",
            github: "https://www.github.com/skarokin/ref-type",
            table: [
                {
                    tech: "React.js & Firebase",
                    purpose: "Frontend Development",
                    results: "State management and real-time updates."
                },
                {
                    tech: "Node.js & Firebase Cloud Functions",
                    purpose: "Backend Development",
                    results: "Real-time leaderboards and user data."
                },
                {
                    tech: "Google Cloud SQL",
                    purpose: "Data Storage",
                    results: "Persistent data storage for user data."
                }
            ]
        },
        {
            title: "MYnote.md",
            description: "Electron-based Markdown note-taking app with LaTeX and code block support",
            date: "May 2023 - Jun 2023",
            link: "",
            github: "https://www.github.com/skarokin/mynote.md",
            table: [
                {
                    tech: "Node.js & Electron",
                    purpose: "Desktop App Development",
                    results: "Cross-platform desktop app with native file system access."
                },
                {
                    tech: "Markdown.it",
                    purpose: "Markdown Parsing",
                    results: "Parse and render Markdown with LaTeX and code block support."
                },
                {
                    tech: "CodeMirror",
                    purpose: "Note Editing",
                    results: "Syntax highlighting and code block editing."
                }
            ]
        }
    ];
</script>

<div class="container flex flex-col items-start gap-2">
    <Tabs.Root value={cards[0].title} class="w-full">
        <!-- horz scroll if too many tabs (mobile) -->
        <div class="overflow-x-auto rounded-lg">
            <Tabs.List class="flex gap-2 w-fit whitespace-nowrap">
              {#each cards as card}
                <Tabs.Trigger class="hover:text-foreground/80 transition-colors" value={card.title}>{card.title}</Tabs.Trigger>
              {/each}
            </Tabs.List>
        </div>
        {#each cards as card}
            <Tabs.Content value={card.title} class="mt-4">
                <Card.Root class="w-full">
                    <Card.Header>
                        <Card.Title>{card.title}</Card.Title>
                        <Card.Description>{card.description}</Card.Description>
                        <Card.Description>
                            <Badge>{card.date}</Badge>
                        </Card.Description>
                    </Card.Header>
                    <Card.Content>
                        {#if card.table}
                            <Table.Root class="text-xs sm:text-sm">
                                <Table.Header>
                                    <Table.Row>
                                        <Table.Head class="sm:w-[150px]"
                                            >Tech</Table.Head
                                        >
                                        <Table.Head class="sm:w-[200px]"
                                            >Purpose</Table.Head
                                        >
                                        <Table.Head>Results</Table.Head>
                                    </Table.Row>
                                </Table.Header>
                                <Table.Body>
                                    {#each card.table as feature, j (j)}
                                        <Table.Row>
                                            <Table.Cell class="font-medium"
                                                >{feature.tech}</Table.Cell
                                            >
                                            <Table.Cell
                                                >{feature.purpose}</Table.Cell
                                            >
                                            <Table.Cell
                                                >{feature.results}</Table.Cell
                                            >
                                        </Table.Row>
                                    {/each}
                                </Table.Body>
                            </Table.Root>
                        {/if}
                    </Card.Content>
                    <Card.Footer>
                        <div class="flex flex-row gap-4">
                            <!-- if no link, only show GitHub with default variant. otherwise, GitHub is outline and Visit is default -->
                            {#if card.link}
                                <a
                                    href={card.link}
                                    target="_blank"
                                    class={buttonVariants({ variant: "default" })}
                                >
                                    Visit
                                </a>
                                <a
                                    href={card.github}
                                    target="_blank"
                                    class={buttonVariants({ variant: "outline" })}
                                >
                                    GitHub
                                </a>
                            {:else}
                            <a
                                href={card.github}
                                target="_blank"
                                class={buttonVariants({ variant: "default" })}
                            >
                                GitHub
                            </a>
                            {/if}
                        </div>
                    </Card.Footer>
                </Card.Root>
            </Tabs.Content>
        {/each}
    </Tabs.Root>
</div>
