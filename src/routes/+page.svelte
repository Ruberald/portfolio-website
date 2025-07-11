<script>
    import Code from "./code.svelte";
</script>

<svelte:head>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Fira+Code:wght@400;600&display=swap" rel="stylesheet">
</svelte:head>

<div class="min-h-screen flex flex-col bg-zinc-800 bg-gradient-to-b from-zinc-900 to-zinc-800 px-10 lg:px-40 text-center h-full w-screen font-mono text-teal-200 animate-fadeIn">
    <h1 class="text-4xl font-bold mt-8 mb-2 tracking-wider">Heinrich Skies</h1>
    <h2 class="text-2xl font-thin mb-6">aka Sajid Hossain</h2>

    <Code />
</div>

<style>
  :global(html) {
    font-family: 'Fira Code', monospace;
  }

  @keyframes fadeIn {
    from { opacity: 0; transform: translateY(20px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  .animate-fadeIn {
    animation: fadeIn 1s ease-out forwards;
  }
</style>
