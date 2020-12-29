<script>
    import { openSite } from "./Skills.svelte";
    import { fade } from "svelte/transition";

    let visible = false;

    function toggleVisible() {
        visible = !visible;
    }

    const educationItems = [
        {
            school: {
                name: "New York University",
                site: "http://www.nyu.edu/",
            },
            location: "Brooklyn, NY",
            degree: "M.S. Computer Science",
            gpa: 3.8,
            dates: "Sep 2018 - May 2020",
            relevantCourses: [
                "Application Security",
                "Security Engineering & Management",
                "Security Analytics",
                "Big Data",
                "Network Security",
                "Digital Forensics",
                "Computer Security",
                "Computer networking",
                "Database Design & Management",
                "Design & Analysis of Algorithms",
            ],
        },
        {
            school: {
                name: "Northern Virginia Community College",
                site: "https://www.nvcc.edu/",
            },
            location: "Manassas, VA",
            degree: "Continuing Education",
            gpa: 4.00,
            dates: "May 2017 - May 2018",
            relevantCourses: [
                "Linear Algebra",
                "Computer Organization",
                "Discrete Mathematics",
                "Data Structures",
            ],
        },
        {
            school: {
                name: "College of William and Mary",
                site: "https://www.wm.edu/",
            },
            location: "Williamsburg, VA",
            degree: "B.S. Neuroscience",
            gpa: 3.14,
            dates: "Sep 2011 - May 2015",
            relevantCourses: [
                "Concepts in Computer Science",
                "Computational Problem Solving",
            ],
        },
    ];
</script>

<style>
    .education-history {
        width: 500px;
        margin: auto;
    }
    .edu:hover{
        box-shadow: 0px 2px 4px rgba(0, 0, 0, 1);
        transform: translateX(-2px);
    }

    .right {
        float: right;
    }

    .left {
        float: left;
    }

    #school-link {
        text-decoration: underline;
    }

    #school-link:hover {
        color: blue;
    }
    #school-link:active {
        color: purple;
    }

    .education {
        width: 500px;
        margin: auto;
        padding: 20px;
    }
    .education-box-1 {
        margin: auto;
        padding: 10px;
    }
    .education-box-2 {
        margin: auto;
        padding: 10px;
    }

    .description-box {
        margin: auto;
        padding: 10px;
    }
</style>

<!-- <div style="cursor: pointer;" onclick="" /> -->

<div class="education-history">
    {#each educationItems as edu}
        <div class="edu">
            <div class="education" on:click={() => toggleVisible()}>
                <div class="education-box-1">
                    <div
                        id="school-link"
                        class="left">
                        <a on:click={() => openSite(edu.school.site)} href="javascript:void(0)"> {edu.school.name}</a>
                    </div>
                    <div class="right">{edu.location}</div>
                </div>
                <div class="education-box-2">
                    <div class="left">{edu.degree} | GPA: {edu.gpa}</div>
                    <div class="right">{edu.dates}</div>
                </div>
            </div>
            {#if visible}
                <div
                    transition:fade={{ y: 200, duration: 500 }}
                    class="description-box">
                    <ul class="show-data">
                        {#each edu.relevantCourses as course}
                            <li>{course}</li>
                        {/each}
                    </ul>
                </div>
            {/if}
        </div>
    {/each}
</div>
