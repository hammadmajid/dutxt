<script lang="ts">
    import favicon from '$lib/assets/favicon.svg';
    import 'terminal.css'

    let {children} = $props();
</script>

<svelte:head>
    <link rel="icon" href={favicon}/>
</svelte:head>

<div class="container-fluid">
    <nav class="terminal-nav">
        <header class="terminal-logo">
            <span class="terminal-prompt">Dutxt</span>
        </header>
        <div class="terminal-menu">
            <ul>
                <li><a href="https://github.com/hammadmajid/dutxt" target="_blank">Source</a></li>
                <li><a href="https://hammadmajid.pages.dev" target="_blank">Author</a></li>
            </ul>
        </div>
    </nav>

    <div>
        {@render children?.()}
    </div>
</div>
