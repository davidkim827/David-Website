<script>
    import { openSite } from "./Skills.svelte";
    import { fade } from "svelte/transition";

    let visible = false;

    function toggleVisible() {
        visible = !visible;
    }

    const workItems = [
        {
            company: {
                name: "Amazon",
                site: "https://www.amazon.com/",
            },
            location: "New York, NY",
            position: "Appsec Automation Engineer",
            dates: "April 2022 - Present",
            descriptions: [
                "Created and released rules to contribute to an in-house built SAST solution ruleset, resulting in proactive prevention of several zero-day vulnerabilities such as potential RCEs, data exfiltration, and more",
                "Automated mass scale rule testing to ensure high fidelity/precision detections (7% FP Rate for all rules written)",
                "Revamped rule creation documentation for efficient workflow and onboarding as well as creating automation scripts for tools' setup",
                "Performed Threat Modeling and Design Review consultations for dev teams creating / releasing services",
                "Researched and implemented code abstractions to data flow detections, resulting in approximately 95%+ reduction in time spent on rule writing",
                "Trained external teams on tools usage",
                "Mentored and taught several junior members on team",
            ],
        },
        {
            company: {
                name: "Northwestern Mutual Insurance",
                site: "https://www.northwesternmutual.com/",
            },
            location: "New York, NY",
            position: "Security Automation Engineer",
            dates: "May 2021 - Present",
            descriptions: [
                "Developed Encoder/Decoder Splunk app in Python for Threat Detection team, reducing time spent on SPL search development by 25%",
                "Developed Splunk app for Insider Threat team to allow users' Slack usage auditing",
                "Fuzzed own apps using atheris to ensure minimal bugs",
                "Migrated existing codebases from Python 2.x to 3.x and incorporated CI/unit testing to code repos",
                "Created Phantom SOAR playbooks to automate existing IR manual processes, reducing workflow times by 50%+",
                "Configured Splunk Phantom Addon to automatically send notable events to Phantom",
            ],
        },
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
        {
            company: {
                name: "Command Group",
                site: "https://www.commandcg.com/",
            },
            location: "Washington, DC",
            position: "Sec Advisory and Mgmt Services",
            dates: "Sept 2016 – May 2017",
            descriptions: [
                "Created reports on OSINT regarding security concerns to clients",
                "Researched business development opportunities in the Middle East",
                "Created daily briefs for company executives on latest trends and topics in National and Homeland security matters",
            ],
        },
    ];
</script>

<!-- <div style="cursor: pointer;" onclick="" /> -->

<div class="work-history">
    {#each workItems as work}
        <div class="work">
            <div class="career" on:click={() => toggleVisible()}>
                <div class="career-box-1">
                    <div id="company-link" class="left">
                        <a
                            on:click={() => openSite(work.company.site)}
                            href="javascript:void(0)"
                        >
                            {work.company.name}
                        </a>
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
                    class="description-box"
                >
                    <ul class="show-data">
                        {#each work.descriptions as description}
                            <li class="item">{description}</li>
                        {/each}
                    </ul>
                </div>
            {/if}
        </div>
    {/each}
</div>

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
        padding: 18px;
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

    .item {
        margin: 10px;
    }
</style>
