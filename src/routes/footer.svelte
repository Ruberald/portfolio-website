<script>
    let socials = [
        { name: "Instagram", link: "https://www.instagram.com/sajid.is.it/", path: "assets/instagram.svg" },
        { name: "Github", link: "https://github.com/Ruberald", path: "assets/github.svg" },
        { name: "Twitter", link: "https://twitter.com/heinrichskies", path: "assets/twitter.svg" },
        { name: "YouTube", link: "https://www.youtube.com/@ruberald", path: "assets/youtube.svg" }
    ];
</script>

<footer class="flex justify-end w-full pr-6 mt-4">
    <ul class="flex space-x-4">
        {#each socials as social}
            <li>
                <a href="{social.link}" target="_blank" rel="noopener noreferrer" aria-label={social.name}>
                    <img
                        src="{social.path}"
                        alt="{social.name}"
                        class="h-6 w-6 transition-transform duration-300 transform hover:scale-125 glowing-icon"
                    />
                </a>
            </li>
        {/each}
    </ul>
</footer>

<style>
  footer {
    background: transparent;
  }

  .glowing-icon {
    filter: brightness(0.8) drop-shadow(0 0 2px #00ff80);
    transition: filter 0.3s ease, transform 0.3s ease;
  }

  .glowing-icon:hover {
    filter: brightness(1.2) drop-shadow(0 0 6px #00ffcc);
    transform: scale(1.25);
  }
</style>
