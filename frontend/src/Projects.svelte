<script>
    import { openSite } from "./Skills.svelte";
    import { fade } from "svelte/transition";

    let visible = false;

    function toggleVisible() {
        visible = !visible;
    }

    const projectItems = [
        {
            project: { name: "Security Assessment", date: "May 2020", site: "https://www.synopsys.com/glossary/what-is-security-risk-assessment.html"},
            description: [
                "Performed security assessment for the MakerSpace Department at NYU including: 1) Physical/Operational Security Testing 2) Infrastructure/DAST Scanning",
                "Documented all vulnerabilities and made recommendations to secure MakerSpace in a formal report; solutions were utilized to harden infrastructure",
            ],
        },
        {
            project: { name: "Windows Registry Analytics", date: "May 2019", site: "https://www.youtube.com/watch?v=ak-6j0cGxts"},
            description: [
                "Created script to walk the Windows Registry, analyzing data for any executable files residing within the registry",
                "https://www.youtube.com/watch?v=ak-6j0cGxts"
            ],

        },
        {
            project: { name: "File Analytics", date: "May 2019", site: "https://github.com/davidkim827/BigData/tree/master/Project%203"},
            description: [
                "Created script converting PDF and DOCX files into text data and placed into CSV for analytics",
                "Utilized Supervised Machine Learning to analyze text and train model to predict category based on text"
            ],
        },
        {
            project: { name: "Screenshot Bot", date: "Dec 2018", site: "https://github.com/davidkim827/Screenshot-Bot"},
            description: [
                "Created script to automate full screen capture of 500+ webpages using Selenium WebDriver API/Python to reduce time spent by 95%+",
            ],
        }
    ];
</script>

<style>
    .project-history {
        width: 500px;
        margin: auto;   
    }

    .proj:hover{
        box-shadow: 0px 2px 4px rgba(0, 0, 0, 1);
        transform: translateX(-2px);
    }

    .right {
        float: right;
    }

    .left {
        float: left;
    }

    #project-link {
        text-decoration: underline;
    }

    #project-link:hover {
        color: blue;
    }
    #project-link:active {
        color: purple;
    }

    .project {
        width: 500px;
        margin: auto;
        padding: 20px;
    }
    .project-box-1 {
        margin: auto;
        padding: 10px;
    }
    .description-box {
        margin: auto;
        padding: 10px;
    }
</style>

<!-- <div style="cursor: pointer;" onclick="" /> -->

<div class="project-history">
    {#each projectItems as proj}
        <div class=proj>
        <div class="project" on:click={() => toggleVisible()}>
            <div class="project-box-1">
                <div
                    id="project-link"
                    class="left"
                    on:click={() => openSite(proj.project.site)}>
                    {proj.project.name}
                </div>
                <div class="right">{proj.project.date}</div>
            </div>
        </div>
        {#if visible}
            <div
                transition:fade={{ y: 200, duration: 500 }}
                class="description-box">
                <ul class="show-data">
                    {#each proj.description as desc}
                        <li>{desc}</li>
                    {/each}
                </ul>
            </div>
        {/if}
        </div>
    {/each}
</div>
