<script lang="ts">
    import { base } from '$app/paths'
    import { page } from '$app/stores'
    import { onMount } from 'svelte'

    let links = [
        { href: '/', text: '主页' },
        { href: '/joker', text: '新建小丑牌' },
    ]
</script>

<nav>
    <ul class="NotoSansSC-Bold flex flex-row gap-4 text-2xl">
        {#each links as link}
            <li>
                {#if $page.url.pathname === base + link.href}
                    <p class="underline underline-offset-4">{link.text}</p>
                {:else}
                    <a href="{base}{link.href}">{link.text}</a>
                {/if}
            </li>
        {/each}
    </ul>
</nav>
