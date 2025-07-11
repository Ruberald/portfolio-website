<script>
    import Footer from "./footer.svelte";

    import { onMount } from "svelte";
    let showProjects = false;
    let showLangs = false;

    function toggleProjects() {
        showProjects = !showProjects;
        showLangs = false;
    }

    function toggleLangs() {
        showLangs = !showLangs;
        showProjects = false;
    }
</script>

<div class="monitor-frame mb-10">
<div class="crt-screen flex flex-grow bg-gray-900 m-4 p-10 rounded-lg shadow-lg transition-all duration-500 ease-in-out">
    <span class="main flex-grow">
        <pre class="text-left whitespace-pre-line">
            <code class="text-sky-200 text-m"> #include &lt;experience&gt;

                class <b>Portfolio</b> 
                &lcub;
                <pre class="text-left">
    public:

    // source for this 
    <a href="https://github.com/Ruberald/portfolio-website" 
    target="_blank"
    title="View on GitHub" 
    class="link"> Portfolio();
    </a>
    // view projects
    <b title="struct containing projects">Projects </b> 
    <a href="javascript:void(0);" title="Projects" on:click={toggleProjects} class="link"> getProjects();</a>

    // languages 
    <b title="struct containing languages">Languages </b> 
    <a href="javascript:void(0);" title="Languages" on:click={toggleLangs} class="link"> getLanguages(); </a> </pre> &rcub; </code>
        </pre>
    </span>

    {#if showProjects}
        <span class="side bg-teal-800 m-4 p-4 rounded-lg flex-grow fade-in">
            <pre class="text-left whitespace-pre-line">
                <code class="text-sky-100 text-sm">
                <pre class="text-left whitespace-pre">
struct Projects &lcub;
    Project projects[] = &lcub;
        <a href="https://github.com/Ruberald/Chip-8-emulator" class="link" target="_blank">Emulator</a>,
        <a href="https://github.com/Ruberald/search-engine-cc" class="link" target="_blank">Search_Engine</a>,
        <a href="https://github.com/Ruberald/hack-assembler-rs" class="link" target="_blank">Assembler</a>,
    &rcub;;
    Link <a href="https://github.com/Ruberald?tab=repositories" class="link" target="_blank">more</a>;
&rcub;;
                </pre>
                </code>
            </pre>
        </span>
    {:else if showLangs}
        <span class="side bg-teal-800 m-4 p-4 rounded-lg flex-grow fade-in">
            <pre class="text-left whitespace-pre-line">
                <code class="text-sky-100 text-sm">
                <pre class="text-left whitespace-pre">
struct Languages &lcub;
    Project projects[] = &lcub;
        <a href="https://github.com/Ruberald/Chip-8-emulator" class="link" target="_blank">Emulator</a>,
        <a href="https://github.com/Ruberald/search-engine-cc" class="link" target="_blank">Search_Engine</a>,
        <a href="https://github.com/Ruberald/hack-assembler-rs" class="link" target="_blank">Assembler</a>,
    &rcub;;
    Link <a href="https://github.com/Ruberald?tab=repositories" class="link" target="_blank">more</a>;
&rcub;;
                </pre>
                </code>
            </pre>
        </span>
    {/if}


</div>

<div class="monitor-buttons">
    <Footer />
</div>

</div>

<style>
  .link {
    @apply hover:text-sky-400 hover:translate-x-2 transition-transform duration-300 inline-block;
  }

  .fade-in {
    animation: fade-in 0.5s ease-out;
  }

  @keyframes fade-in {
    from { opacity: 0; transform: translateY(10px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  @import url('https://fonts.googleapis.com/css2?family=Fira+Code&display=swap');

    .monitor-buttons {
      display: flex;
      justify-content: center;
      gap: 1rem;
      padding-top: 0rem;
      /* border-top: 1px solid rgba(0, 255, 128, 0.2);*/
      margin-top: 0rem;
      z-index: 2;
      position: relative;
    }

    .monitor-buttons a img {
      width: 20px;
      height: 20px;
      filter: brightness(0.8) drop-shadow(0 0 2px #00ff80);
      transition: transform 0.2s ease, filter 0.3s ease;
    }

    .monitor-buttons a:hover img {
      filter: brightness(1.2) drop-shadow(0 0 4px #00ffcc);
      transform: scale(1.2);
    }

  .monitor-frame {
    padding: 2rem;
    border-radius: 1rem;
    background: radial-gradient(ellipse at center, #222 0%, #000 100%);
    box-shadow:
      0 0 20px rgba(0, 255, 0, 0.3),
      inset 0 0 50px rgba(0, 255, 0, 0.1),
      0 0 60px #00ff80;
    border: 4px solid #111;
  }

  .crt-screen {
    background: #0d0d0d;
    color: #00ff80;
    font-family: 'Fira Code', monospace;
    padding: 1.5rem;
    border-radius: 0.5rem;
    position: relative;
    overflow: hidden;
    box-shadow:
      inset 0 0 10px #00ff80,
      inset 0 0 20px #00ff80,
      0 0 40px rgba(0, 255, 128, 0.2);
    animation: flicker 5s infinite ease-in-out;
  }

  .crt-screen::before {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: repeating-linear-gradient(
      to bottom,
      rgba(0, 255, 128, 0.05),
      rgba(0, 255, 128, 0.05) 1px,
      transparent 1px,
      transparent 2px
    );
    pointer-events: none;
    z-index: 1;
  }

    .crt-wrapper {
      perspective: 800px;
      display: flex;
      justify-content: center;
    }

    .crt-screen {
      transform: rotateX(1deg) rotateY(1deg) scale(1);
      border-radius: 12px;
      position: relative;
      background: #0d0d0d;
      color: #00ff80;
      font-family: 'Fira Code', monospace;
      padding: 1.5rem;
      overflow: hidden;
      box-shadow:
        inset 0 0 15px #00ff80,
        inset 0 0 30px rgba(0, 255, 128, 0.3),
        0 0 40px rgba(0, 255, 128, 0.2);
      animation: flicker 5s infinite;
    }

    /* Curved glass highlight */
    .crt-screen::after {
      content: "";
      position: absolute;
      top: -10%;
      left: -10%;
      width: 120%;
      height: 120%;
      background: radial-gradient(ellipse at center, rgba(255,255,255,0.06), transparent 70%);
      mix-blend-mode: screen;
      pointer-events: none;
      border-radius: 50%;
      z-index: 2;
    }

  .crt-content {
    z-index: 2;
    position: relative;
  }

@keyframes flicker {
  0% {
    opacity: 0.9;
    filter: brightness(0.55) blur(0px);
  }
  5% {
    opacity: 0.6;
    filter: brightness(1.45) blur(0.5px);
  }
  10% {
    opacity: 0.95;
    filter: brightness(0.5) blur(0.25px);
  }
  12.5% {
    opacity: 0.5;
    filter: brightness(1.4) blur(0.5px);
  }
  15% {
    opacity: 0.8;
    filter: brightness(1) blur(0.2px);
  }
  100% {
    opacity: 0.95;
    filter: brightness(1) blur(0);
  }
}

  a {
    color: inherit;
    text-decoration: none;
  }

  a:hover {
    color: #1affd5;
    text-shadow: 0 0 5px #00ffd5;
  }

  .side {
    margin-top: 1rem;
    background-color: rgba(0, 255, 128, 0.05);
    padding: 1rem;
    border: 1px solid #00ff80;
    border-radius: 0.5rem;
  }

  /* Optional scrollbar styling */
  .crt-screen::-webkit-scrollbar {
    width: 8px;
  }

  .crt-screen::-webkit-scrollbar-thumb {
    background-color: #00ff80;
  }
  
</style>
