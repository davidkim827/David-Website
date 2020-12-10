<script>
    import { openSite } from "./Skills.svelte";
    import { fade } from "svelte/transition";

    let visible = false;

    function toggleVisible() {
        visible = !visible;
    }

    const workItems = [
        {
            company: { name: "HSBC", site: "https://www.hsbc.com/" },
            location: "Jersey City, NJ",
            position: "Security Automation Engineer",
            dates: "Nov 2019 - Nov 2020",
            descriptions: [
                "Created and maintained in-house built vulnerability assessment to: 1) score vulnerabilities, 2) schedule vulnerability information updates 3) schedule data uploads to data aggregation platform (Kenna) ",
                "Built out bridge APIs for security scanning tools to automate security scanning (SAST/DAST/Infrastructure)",
                "Helped create in-house platform to allow application security & other dev teams to run security scans",
                "Created URL whitelisting service used by 20,000 developers",
            ],
        },
        {
            company: {
                name: "NYC Dept. of Finance",
                site: "https://www1.nyc.gov/site/finance/index.page",
            },
            location: "New York, NY",
            position: "Network Operations",
            dates: "Jun 2019 – Nov 2019",
            descriptions: [
                "Created Software Management and Deployment Proof-of-Concept for IT Dept through setting up Nexus Server and Chocolatey endpoints to interface and auto-install software on to Windows terminals",
                "Configured software on Windows/RHEL based servers for the purposes of network security, automation, and CI/CD for the DevSecOps team",
            ],
        },
    ];
</script>

<style>
    .work-history {
        width: 500px;
        margin: auto;
    }

    .work:hover {
        box-shadow: 0px 2px 4px rgba(0, 0, 0, 1);
        transform: translateX(-2px);
    }

    .right {
        float: right;
    }

    .left {
        float: left;
    }

    #company-link {
        text-decoration: underline;
    }

    #company-link:hover {
        color: blue;
    }
    #company-link:active {
        color: purple;
    }

    .career {
        width: 500px;
        margin: auto;
        padding: 20px;
    }
    .career-box-1 {
        margin: auto;
        padding: 10px;
    }
    .career-box-2 {
        margin: auto;
        padding: 10px;
    }

    .description-box {
        margin: auto;
        padding: 10px;
    }
</style>

<!-- <div style="cursor: pointer;" onclick="" /> -->

<div class="work-history">
    {#each workItems as work}
        <div class="work">
            <div class="career" on:click={() => toggleVisible()}>
                <div class="career-box-1">
                    <div
                        id="company-link"
                        class="left"
                        on:click={() => openSite(work.company.site)}>
                        {work.company.name}
                    </div>
                    <div class="right">{work.location}</div>
                </div>
                <div class="career-box-2">
                    <div class="left">{work.position}</div>
                    <div class="right">{work.dates}</div>
                </div>
            </div>
            {#if visible}
                <div
                    transition:fade={{ y: 200, duration: 500 }}
                    class="description-box">
                    <ul class="show-data">
                        {#each work.descriptions as description}
                            <li>{description}</li>
                        {/each}
                    </ul>
                </div>
            {/if}
        </div>
    {/each}
</div>
