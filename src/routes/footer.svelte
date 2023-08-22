<script>
    let socials = [
        {name: "Instagram", link: "https://www.instagram.com/sajid.is.it/", path: "assets/instagram.svg"},
        {name: "Github", link: "https://github.com/Ruberald", path: "assets/github.svg"},
        {name: "Twitter", link: "https://twitter.com/heinrichskies", path: "assets/twitter.svg"},
        {name: "YouTube", link: "https://www.youtube.com/@ruberald", path: "assets/youtube.svg"}
    ] 
</script>

<footer class="bg-zinc-800 flex flex-row m-5">
    <div class="container mx-auto flex justify-center items-center">
        <ul class="flex space-x-4">
            {#each socials as social}
                <li>
                    <a href="{social.link}">
                        <img class="h-5 w-5" src="{social.path}" alt="{social.name}">
                    </a>
                </li>
            {/each}
        </ul>
    </div>
</footer>
