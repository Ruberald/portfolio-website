<script>
    import { onMount } from "svelte";

    let showProjects = false;

    onMount(() => {
        // You can add logic here to fetch and load your projects data if needed
    });

    function toggleProjects() {
        showProjects = !showProjects;
    }
</script>

<div class="flex bg-gray-900 m-4 p-4 rounded-lg ">
    <span class="main flex-grow">
        <pre class="text-left whitespace-pre-line">
            <code class="text-sky-200 text-sm">
                #include &lt;experience&gt;

                class <b>Portfolio</b> 
                &lcub;
                <pre class="text-left whitespace-pre">
    public:

    // source for this <a href="https://github.com/Ruberald/portfolio-website" 
    target="_blank"
    title="View on GitHub" 
    class="hover:shadow-md hover:text-sky-400 hover:translate-x-2 transition transform duration-300">
    Portfolio();
    </a>
    // view projects
    <b title="struct containing projects">Projects </b> <a href="javascript:void(0);" 
    title="View on GitHub" 
    on:click={toggleProjects}
    class="hover:shadow-md hover:text-sky-400 hover:translate-x-2 transition transform duration-300">
    getProjects();
    </a>
                </pre>
                &rcub;
            </code>
        </pre>
    </span>
    {#if showProjects}
        <span class="side bg-teal-800 m-4 p-4 rounded-lg flex-grow">
            <pre class="text-left whitespace-pre-line">
                <code class="text-sky-100 text-sm">
                <pre class="text-left whitespace-pre">
struct Projects &lcub;
    Project projects[] = &lcub;
        <a href="https://github.com/Ruberald/Chip-8-emulator" class="hover:text-sky-400" target="_blank">Emulator</a>,
        <a href="https://github.com/Ruberald/search-engine-cc" class="hover:text-sky-400" target="_blank">Search_Engine</a>,
        <a href="https://github.com/Ruberald/hack-assembler-rs" class="hover:text-sky-400" target="_blank">Assembler</a>,
    &rcub;;
    Link <a href="https://github.com/Ruberald?tab=repositories" class="hover:text-sky-400" target="_blank">more</a>;
&rcub;;
                </pre>
                </code>
            </pre>
        </span>
    {/if}
</div>
