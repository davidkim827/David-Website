<script>
    import { Tabs, TabList, TabPanel, Tab } from "./Tabs/tabs.js";
    import WorkHistory from "./WorkHistory.svelte";
    import Education from "./Education.svelte"
    import Projects from "./Projects.svelte"
</script>


<Tabs>
    <TabList class="tablist">
        <Tab><h3>Work Experience</h3></Tab>
        <Tab><h3>Education</h3></Tab>
        <Tab><h3>Projects</h3></Tab>
    </TabList>

    <TabPanel>
        <WorkHistory />
    </TabPanel>
    <TabPanel>
        <Education/>
    </TabPanel>
    <TabPanel>
        <Projects/>
    </TabPanel>
</Tabs>