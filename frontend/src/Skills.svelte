<script context="module">
    export function openSite(site) {
        window.open(site, "_blank");
    }

    const skills = [
        {
            skill: "Security Automation",
            site: "https://securitytrails.com/blog/security-automation",
        },
        {
            skill: "AppSec/Security Tooling",
            site: "https://en.wikipedia.org/wiki/Application_security",
        },
        {
            skill: "Vulnerability Assessments",
            site:
                "https://searchsecurity.techtarget.com/definition/vulnerability-assessment-vulnerability-analysis",
        },
        {
            skill: "Web Development",
            site: "https://en.wikipedia.org/wiki/Web_development",
        },
        { skill: "Python", site: "https://www.python.org/" },
        { skill: "JS (Svelte)", site: "https://svelte.dev/" },
        {
            skill: "Data Analytics",
            site: "https://en.wikipedia.org/wiki/Data_analysis",
        },
        {
            skill: "Databases (SQL/NoSQL)",
            site: "https://www.mongodb.com/nosql-explained/nosql-vs-sql",
        },
        {
            skill: "Microservices",
            site: "https://en.wikipedia.org/wiki/Microservices",
        },
    ];
</script>

<style>
    .flex-parent {
        display: flex;
        flex-wrap: wrap;
        width: 500px;
        align-items: center;
        justify-content: center;
        align-content: center;
        margin-top: 25px;
        margin-bottom: 50px;
        margin-right: auto;
        margin-left: auto;
    }

    .jc-center {
        justify-content: center;
    }

    button.buttons {
        text-align: center;
        border-radius: 20px;
        display: flex;
        margin-right: 5px;
        padding: 1em;
    }

    button {
        border-radius: 4px;
        box-shadow: 0px 8px 15px rgba(0, 0, 0, 0.1);
        border: none;
        color: #000;
        background-color: #fff;
        text-align: center;
        padding: 50px;
        width: auto;
        transition: all 0.5s;
        cursor: pointer;
        margin: 1px;
        cursor: pointer;
        display: inline-block;
    }

    button:hover {
        background-color: #24a0ed;
        box-shadow: 0px 15px 20px rgba(0, 0, 0, 0.1);
        color: #fff;
        transform: translateY(-7px);
    }

    button span:after {
        content: " >";
        position: relative;
        opacity: 0;
        transition: 0.5s;
    }

    button:hover span {
        padding-right: 2px;
    }

    button:hover span:after {
        opacity: 1;
    }
</style>

<div class="flex-parent jc-center">
    {#each skills as skill, i}
        {#if i % 3 == 0}<br />{/if}
        <button
            type="button"
            class="buttons"
            on:click={() => openSite(skill.site)}>
            <span>{skill.skill}</span>
        </button>
    {/each}
</div>
